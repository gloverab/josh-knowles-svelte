<script>
  import RouterLink from './RouterLink.svelte';
</script>

<div id='nav-links'>
  <RouterLink page={{path: '/about', name: 'About'}} />
  <!-- <RouterLink page={{path: '/video', name: 'Video'}} /> -->
  <RouterLink page={{path: '/selected-works', name: 'Selected Works'}} />
  <!-- <RouterLink page={{path: '/shows', name: 'Shows'}} /> -->
  <RouterLink page={{path: '/press', name: 'Press'}} />
  <RouterLink page={{path: '/contact', name: 'Contact'}} />
</div>

<style>
  #nav-links {
    display: flex;
    height: 100%;
  }

  @media (max-width: 600px) {
    #nav-links {
      height: 50%;
      width: 100%;
      flex-direction: column;
      justify-content: space-between;
    }
  }
</style>