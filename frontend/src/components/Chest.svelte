<script lang="ts">
  import { pickChest } from '../Facade'
  import roomStore from '../stores/Room'
</script>

{#if $roomStore.chest !== undefined}
  <h3>Chest</h3>

  {#if $roomStore.chest.item.quantity > 0}
    <p>Contains {$roomStore.chest.item.quantity} {$roomStore.chest.item.name}</p>

    <div class="action-container">
      <button on:click={pickChest}>
        Pick 1 item
      </button>
    </div>
  {:else}
    <div class="sorry-man">It's empty :(</div>
  {/if}
{/if}

<style>
  p {
    margin: 1.2rem 0;
  }

  button {
    margin: 0 auto;
  }
</style>