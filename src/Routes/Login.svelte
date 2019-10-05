<script>
  import { navigate } from "svelte-routing";
  let username;
  let password;
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<form
  on:submit={e => {
    e.preventDefault();
    console.log(e);
    navigate('/list');
    return false;
  }}>
  <input bind:value={username} placeholder="Username" />
  <input bind:value={password} type="password" placeholder="password" />

  <input type="submit" value="Log In" />
</form>
