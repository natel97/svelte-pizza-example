<script>
  import OptionCard from "./Partials/OptionCard.svelte";

  export let name = "";
  export let options = [];
  export let multiple = false;
  export let sizes = false;
  export let selection;

  const handleSet = item => {
    if (multiple) {
      if (selection[item]) {
        selection[item] = false;
      } else {
        selection[item] = true;
      }
    } else {
      if (selection[item]) {
        selection[item] = false;
      } else {
        Object.keys(selection).forEach(key => (selection[key] = false));
        selection[item] = true;
      }
    }
  };
</script>

<div>Select a{multiple ? `s many ${name} as you'd like` : ` ${name}`}</div>
<div class="flex-row wrap">
  {#each options as opt}
    <OptionCard name={opt} {handleSet} selected={selection[opt]} />
  {/each}
</div>
