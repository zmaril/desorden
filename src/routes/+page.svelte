<script>
    import { WebPlayback } from 'svelte-spotify-web-playback';
    import CustomPlayer from '../player.svelte';
    const client_id = '4e64555654894d41b0878d4efb7a4c15';
    let wrapper; // Reference to our wrapper element.
    let player;
  </script>
  
  <WebPlayback 
  {client_id} 
  name="My Spotify Player" 
  volume={0.5} 
  bind:this={wrapper}
>

  <div slot="login">
      <button on:click={() => wrapper.login()}>Login with Spotify</button>
  </div>

  <CustomPlayer slot="player" let:player let:state {player} {state} />
</WebPlayback>

