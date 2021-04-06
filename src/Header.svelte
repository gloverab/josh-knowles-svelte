<script>
  import { curRoute } from './router.js';
  import SocialLinks from './SocialLinks.svelte';
  import NavLinks from './NavLinks.svelte';
  import { drawerOpen } from './stores.js';

  function redirectTo(event){
    // change current router path
    curRoute.set('/home');
    // push the path into web browser history API
    window.history.pushState({path: '/home'}, '', window.location.origin + '/home');
  }
</script>

<header class='shadow'>
  <div class='left-side'>
    <a href='/home' on:click|preventDefault={redirectTo} id='h1-wrapper'><h1>Josh Knowles</h1></a>

    <div id='nav-wrapper' class='desktop-only'>
      <NavLinks />
    </div>
  </div>

  <div id='links-wrapper' class='desktop-only'>
    <SocialLinks />
  </div>

  <div class='right-side mobile-only'>
    <button on:click={() => drawerOpen.set(true)}>
      <h2 id='burger' class='title ib'><i class='fa fa-bars'></i></h2>
    </button>
  </div>

</header>

<style>
  header {
    background-color: black;
    height: 72px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 1em;
  }

  h1 {
    text-transform: uppercase;
  }

  .left-side {
    display: flex;
    align-items: center;
    height: 100%;
  }

  .right-side {
    display: flex;
    align-items: center;
    height: 100%;
  }

  #burger {
    color: white;
  }

  #nav-wrapper {
    height: 100%;
  }

  #links-wrapper {
    height: 100%;
  }
  
  #h1-wrapper {
    margin-right: 1em;
  }

  h1 {
    letter-spacing: .2rem;
    font-size: 2em;
    display: inline;
  }

  h1, a {
    color: white;
    font-weight: 300;
  }
</style>