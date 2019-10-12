<script>
  import Pizza from "../Components/Design/Pizza.svelte";
  import Step from "../Components/Design/Steps/Step.svelte";

  let stepIndex = 0;

  let layers = [];

  let steps = [
    {
      name: "Crust",
      options: ["Thin", "Thick", "Pan", "Stuffed"],
      selection: {}
    },
    {
      name: "Sauce",
      options: ["Pizza Sauce", "Alfredo"],
      selection: {}
    },
    {
      name: "Toppings",
      options: [
        "Cheese",
        "Pepperoni",
        "Canadian Bacon",
        "Beef",
        "Chicken",
        "Pork",
        "Italian Sausage",
        "Olives",
        "Mushrooms",
        "Green Peppers"
      ],
      multiple: true,
      amounts: true,
      selection: {}
    }
  ];
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
  <Step {...steps[stepIndex]} />

  <div class="flex-row">
    <div
      class="button is-outlined full-width"
      on:click={() => (stepIndex -= stepIndex === 0 ? 0 : 1)}>
      Back
    </div>
    <div
      class="button is-primary full-width"
      on:click={() => (stepIndex += stepIndex < steps.length - 1 ? 1 : 0)}>
      {stepIndex === steps.length - 1 ? 'Done' : 'Next'}
    </div>
  </div>
</div>
