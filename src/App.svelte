<script>
  import { Router, Link, Route } from "svelte-routing";
  import Login from "./Routes/Login.svelte";
  import PizzaList from "./Routes/PizzaList.svelte";
  import PizzaDesign from "./Routes/PizzaDesign.svelte";
  import Pizza from "./Routes/Pizza.svelte";
</script>

<Router>
  <Route path="" component={Login} />
  <Route path="login" component={Login} />
  <Route path="list" component={PizzaList} />
  <Route path="design" component={PizzaDesign} />
  <Route path="pizza/:id" component={Pizza} />
</Router>
