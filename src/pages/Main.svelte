<script>
  import {title, subTitle, navBar, welcomeBar} from "../stores"
  import map_ireland from "/src/assets/map_ireland.png";
  import {getContext} from "svelte";
  const baronyService = getContext("BaronyService");

  title.set("Donation Services Inc");
  subTitle.set("Sign up or Log in");

  navBar.set({
    bar: welcomeBar
  });
  baronyService.logout();
</script>

<div class="uk-text-center" uk-grid>
  <div class="uk-width-1-2@m">
    <img width="500" src="{map_ireland}" alt="map_ireland">
    <p> Lets do this thing again</p>
  </div>
  <div class="uk-width-1-2@m ">
    <div class="uk-width-2xlarge">
      <h3 class="uk-heading-small uk-flex"> Welcome to Feudal Ireland  </h3>
      <p> Support your local Lord today</p>
    </div>
  </div>
</div>

