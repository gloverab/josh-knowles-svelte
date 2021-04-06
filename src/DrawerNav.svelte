<script>
  import NavLinks from './NavLinks.svelte'
  import SocialLinks from './SocialLinks.svelte'
  import { drawerOpen } from './stores.js'
</script>


{#if $drawerOpen}
  <div id='overlay' on:click={() => drawerOpen.set(false)} />
{/if}
<div id='drawer-nav' class='mobile-only shadow' class:open={$drawerOpen}>
  <NavLinks />

  <div id='social-links-wrapper'>
    <SocialLinks />
  </div>
</div>

<style>
  #drawer-nav {
    position: absolute;
    right: 0;
    top: 0;
    padding: 2rem;
    background-color: rgba(0, 0, 0, .95);
    height: 100vh;
    width: 300px;
    max-width: 100%;
    border-top-left-radius: 9px;
    transform: translate3d(300px, 0, 0);
    transition: .2s ease all;
  }

  #overlay {
    width: 100vw;
    height: 100vh;
    position: absolute;
    top: 0;
    left: 0;
  }

  #drawer-nav.open {
    transform: translate3d(0,0,0)
  }

  #social-links-wrapper {
    position: absolute;
    width: 100%;
    left: 0;
    bottom: 0;
    padding: 2rem;
  }
</style>