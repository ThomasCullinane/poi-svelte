<script>
  import zog from "/src/assets/zog.png";
  import {navBar, mainBar, subTitle, title} from "../stores"
  import ClaimForm from "../components/ClaimForm.svelte";

  title.set("Barony Claim");
  subTitle.set("Claim your Barony!");
  navBar.set({
    bar: mainBar
  });
</script>

<div class="uk-flex-middle uk-text-center" uk-grid>
  <div class="uk-width-1-2@m ">
    <div class="uk-card uk-card-default uk-card-body uk-box-shadow-large uk-width-2xlarge ">
      <ClaimForm/>
    </div>
  </div>
  <div class="uk-width-1-2@m ">
    <div>
      <img width="300" src="{zog}" alt="zog">
    </div>
  </div>
</div>
