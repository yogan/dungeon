<script>
  import Chest from './Chest.svelte'
  import Socket from './Socket.svelte'
  import Workbench from './Workbench.svelte'
  import roomStore from '../stores/Room'
  import gameStore from '../stores/Game'
</script>

<h1>Room<span>(id: {$gameStore.roomId.substr(0, 4)}, {$roomStore.mnemonic})</span></h1>


{#if $roomStore.description}
  <p>{@html ($roomStore.description).replaceAll("\n", "<br>")}</p>
{/if}

{#if $roomStore.chest || $roomStore.workbench || $roomStore.socket}
  <hr>
{/if}

<div>
  <Chest />
  <Workbench />
  <Socket />
</div>

<style lang="scss">
  @import '../style/vars.scss';

  hr {
    width: 70%;
    border: 0;
    height: 0.2rem;
    background: $col-dark-grey;
    margin: 1.6rem auto;
  }

  p {
    margin: 1.2rem 0;
  }

  span {
    font-size: 13px;
    padding-left: 0.4rem;
  }
</style>
