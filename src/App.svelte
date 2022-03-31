<script>
  import { Route, Router } from "svelte-routing";
  import Create from "./library/Create.svelte"
  import Detail from "./library/Detail.svelte";
  import Library from "./library/Library.svelte";

  export let url = "";
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<Router {url}>
  <main>
    <Route path="/create" let:params>
      <Create  />
    </Route>
    <Route path="/books/:id" let:params>
      <Detail id={params.id} />
    </Route>
    <Route path="/">
      <Library />
    </Route>
  </main>
</Router>