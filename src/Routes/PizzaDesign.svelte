<script>
  import Pizza from "../Components/Design/Pizza.svelte";
  import Crust from "../Components/Design/Steps/Crust.svelte";
  import Sauce from "../Components/Design/Steps/Sauce.svelte";
  import Cheese from "../Components/Design/Steps/Cheese.svelte";
  import Toppings from "../Components/Design/Steps/Toppings.svelte";

  let stepIndex = 0;

  let layers = [];

  let steps = [
    {
      name: "Crust",
      component: Crust
    },
    {
      name: "Sauce",
      component: Sauce
    },
    {
      name: "Cheese",
      component: Cheese
    },
    {
      name: "Toppings",
      component: Toppings
    }
  ];

  let currentStep = steps[stepIndex];
</script>

<style>

</style>

<div class="flex-column space-between full-height">
  <nav
    class="breadcrumb is-centered has-succeeds-separator"
    aria-label="breadcrumbs">
    <ul>
      {#each steps as step, i}
        <li class={i > stepIndex ? 'is-active' : ''}>
          <a on:click={() => (stepIndex = i)}>{step.name}</a>
        </li>
      {/each}
    </ul>
  </nav>
  Step: {stepIndex + 1}
  <Pizza />
  <svelte:component this={steps[stepIndex].component} />

  <div class="flex-row">
    <div
      class="button is-outlined full-width"
      on:click={() => (stepIndex -= stepIndex === 0 ? 0 : 1)}>
      Back
    </div>
    <div
      class="button is-primary full-width"
      on:click={() => (stepIndex += stepIndex < steps.length - 1 ? 1 : 0)}>
      Next
    </div>
  </div>
</div>
