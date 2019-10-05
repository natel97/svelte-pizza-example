<script>
  import { navigate } from "svelte-routing";
  let username;
  let password;
</script>

<style>
  form {
    height: 30%;
  }
</style>

<form
  class="flex-column space-around"
  on:submit={e => {
    e.preventDefault();
    console.log(e);
    navigate('/list');
    return false;
  }}>
  <input bind:value={username} placeholder="Username" class="input text" />
  <input
    bind:value={password}
    type="password"
    placeholder="password"
    class="input" />

  <input type="submit" value="Log In" class="button is-primary" />
</form>
