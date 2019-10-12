<script>
  export let name = "";
  export let image = "";
  export let handleSet;
  export let selected;
</script>

<style>
  .card {
    user-select: none;
  }
</style>

<div
  class={`card margin-1 padding-1 ${selected ? 'has-background-primary has-text-white' : ''}`}
  on:click={() => handleSet(name)}>
  <div>{name}</div>
</div>
