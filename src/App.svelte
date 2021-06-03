<script>
  import {setContext} from "svelte";
  import {BaronyService} from "./services/barony-service";
  import Main from "./pages/Main.svelte"
  import Login from "./pages/Login.svelte"
  import Signup from "./pages/Signup.svelte"
  import Report from "./pages/Report.svelte";
  import Claim from "./pages/Claim.svelte";
  import Settings from "./pages/Settings.svelte";
  import Navigator from "./components/Navigator.svelte";
  import Router from "svelte-spa-router";

  setContext("BaronyService", new BaronyService("http://localhost:4000"));

  let routes = {
    "/" : Main,
    "/login": Login,
    "/signup" : Signup,
    "/report": Report,
    "/claim": Claim,
    "/settings" : Settings,
    "/logout" : Main
  }
</script>

<div class="uk-container">
  <Navigator/>
  <Router {routes}/>
</div>
