<script>
  import BaronyList from "../components/BaronyList.svelte";
  import zog from "/src/assets/zog.png";
  import {navBar, mainBar, subTitle, title} from "../stores"

  title.set("Baronies Claimed");
  subTitle.set("Claims so far");
  navBar.set({
    bar: mainBar
  });
</script>

<div class="uk-text-center" uk-grid>
  <div class="uk-width-1-2@m ">
    <div class="uk-card uk-card-default uk-card-body uk-box-shadow-large uk-width-2xlarge ">
      <BaronyList/>
    </div>
  </div>
  <div class="uk-width-1-2@m">
    <img width="300" src="{zog}" alt="zog">
  </div>
</div>
