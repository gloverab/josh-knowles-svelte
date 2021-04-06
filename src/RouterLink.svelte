<script>
  import { curRoute } from './router.js';
  import { drawerOpen } from './stores.js'
  export let page = {
    path: '/home',
    name: 'Home'
    }

  function redirectTo(event){
    drawerOpen.set(false)
    // change current router path
    curRoute.set(event.target.pathname);
    // push the path into web browser history API
    window.history.pushState({path: page.path}, '', window.location.origin + page.path);
  }
</script>

<a href={page.path} class:selected={$curRoute === page.path} on:click|preventDefault={redirectTo}>{page.name}</a>

<style>
  a {
    display: flex;
    text-transform: uppercase;
    height: 100%;
    border-bottom: 2px solid rgba(0,0,0,0);
    display: flex;
    align-items: center;
    padding: 0 10px;
    color: white;
    font-weight: 300;
  }

  a:hover {
    border-bottom: 2px solid white;
  }

  a.selected {
    border-bottom: 3px solid white;
  }
</style>