<script>
  import { Router, Link, Route } from "svelte-routing";
  import Login from "./Routes/Login.svelte";
  import PizzaList from "./Routes/PizzaList.svelte";
  import PizzaDesign from "./Routes/PizzaDesign.svelte";

  export let name;
</script>

<Router>
  <Route path="login" component={Login} />
  <Route path="list" component={PizzaList} />
  <Route path="design" component={PizzaDesign} />
</Router>
