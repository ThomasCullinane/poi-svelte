<script lang="ts">
  import { onMount, getContext } from "svelte";
  const baronyService = getContext("BaronyService");

  let name = "";
  let description = "";
  let category = "";
  let selectedLocation = 0;
  let locations = ["Ulster", "Connaught","Leinster","Munster"]
  let errorMessage = "";


  async function claim() {
    const success = await baronyService.claim(name, description, category, locations[selectedLocation])
    if (success) {

    } else {
      errorMessage = "Claim not completed - some error occurred";
    }
  }
</script>

<form on:submit|preventDefault={claim} class="uk-form-stacked uk-text-left">
  <div class="uk-grid uk-grid-stack">
    <div class="uk-width-1-2@m">
      <div class="uk-margin">
        <label class="uk-form-label" for="form-stacked-text">Enter Claim</label>
        <div class="uk-form-controls">
          <input bind:value={name} class="uk-input" id="form-stacked-text" type="text" name="Barony Name" placeholder="Barony Name">
        </div>
        <div class="uk-form-controls">
          <input bind:value={description} class="uk-input" id="form-stacked-text" type="text" name="Description" placeholder="Description">
        </div>
        <div class="uk-form-controls">
          <input bind:value={category} class="uk-input" id="form-stacked-text" type="text" name="Category" placeholder="Category">
        </div>
      </div>

      <div class="uk-margin">
        <div class="uk-form-label">Location </div>
        <div class="uk-form-controls">
          <label><input bind:group={selectedLocation} value={0} class="uk-radio" type="radio" name="method"> {locations[0]} </label><br>
          <label><input bind:group={selectedLocation} value={1} class="uk-radio" type="radio" name="method"> {locations[1]} </label><br>
          <label><input bind:group={selectedLocation} value={2} class="uk-radio" type="radio" name="method"> {locations[2]} </label><br>
          <label><input bind:group={selectedLocation} value={3} class="uk-radio" type="radio" name="method"> {locations[3]} </label>
        </div>
      </div>
    </div>
    <div class=" uk-width-1-2@m">
      <div class="uk-margin">
        <button class="submit uk-button uk-button-primary uk-button-large uk-width-1-1">Claim</button>
      </div>
      {#if errorMessage}
        <div class="uk-text-left uk-text-small">
          {errorMessage}
        </div>
      {/if}
    </div>
  </div>
</form>
