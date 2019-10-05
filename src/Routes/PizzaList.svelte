<script>
  import { navigate, Link } from "svelte-routing";
  import Pizza from "../Components/Pizza.svelte";
  let pizzas = window.localStorage.getItem("pizza") || [];

  $: window.localStorage.setItem("pizza", pizzas);
</script>

<style>

</style>

<div class="has-margin has-padding flex-column space-between full-height">
  <div class="flex-row wrap">
    {#each pizzas as pizza}
      <Link to={`/pizza/${pizza}`}>
        <Pizza {pizza} />
      </Link>
    {/each}
  </div>
  <div class="button is-primary margin-1" on:click={() => navigate('design')}>
    Add Pizza
  </div>

</div>
