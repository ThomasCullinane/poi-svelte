<script>
  import {getContext, onMount} from 'svelte'

  const baronyService = getContext("BaronyService");
  let baronyList = [];

  onMount(async () => {
    baronyList = await baronyService.getBaronies();
  });
</script>

<h3 class="uk-heading-divider">
  Current Baronies </h3>
<div class="uk-table uk-table-divider">
  <table class="uk-table">
    <thead>
      <th>
        Name
      </th>
      <th>
        Description
      </th>
      <th>
        Location
      </th>
    </thead>
    <tbody class="uk-text-left">
      {#each baronyList as barony}
        <tr>
          <td>
            {barony.name}
          </td>
          <td>
            {barony.description}
          </td>
          <td>
            {barony.location}
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>
