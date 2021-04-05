<script>
  import RouterLink from './RouterLink.svelte';

  let menuExpanded = false
</script>

<header class='shadow'>
  <div class='left-side'>
    <a href='/' id='h1-wrapper'><h1 class='desktop-only'>Josh Knowles</h1></a>

    <h2 class='title ib mobile-only' onClick={this.expandMenu}><i class='fa fa-bars'></i></h2>

    <!-- <h1 class='title mobile ib mobile-only'><a href='/'>Josh Knowles</a></h1> -->

    <a href='/' class='mobile-only'><h2>Josh Knowles</h2></a>

    <li class='header-nav-li header-nav-li-nav mobile-only ib' onClick={this.expandMenu}><a href='/'>Home</a></li>
    <RouterLink page={{path: '/home', name: 'Home'}} />
    <RouterLink page={{path: '/about', name: 'About'}} />
    <RouterLink page={{path: '/video', name: 'Video'}} />
    <RouterLink page={{path: '/music', name: 'Music'}} />
    <RouterLink page={{path: '/shows', name: 'Shows'}} />
    <RouterLink page={{path: '/press', name: 'Press'}} />
    <RouterLink page={{path: '/contact', name: 'Contact'}} />
  </div>

  <div class='right-side'>
    <a href='https://music.apple.com/us/artist/josh-knowles/635148421' class='nav-icon'><i class='fa fa-apple'></i></a>
    <a href='https://open.spotify.com/artist/2cYJgCe7KbXn1Y4TL0JCrK?si=cMotAAjRSsO0C6EJOyymZw' class='nav-icon'><i class='fa fa-spotify'></i></a>
    <a href='https://www.facebook.com/joshknowlesmusic' class='nav-icon'><i class='fa fa-facebook'></i></a>
    <a href='https://www.twitter.com/joshnemes' class='nav-icon'><i class='fa fa-twitter'></i></a>
    <a href='https://www.instagram.com/joshnemes' class='nav-icon'><i class='fa fa-instagram'></i></a>
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

  a {
    display: flex;
    align-items: center;
    text-transform: uppercase;
    height: 100%;
    border-bottom: 2px solid rgba(0,0,0,0);
  }

  .nav-item, .nav-icon {
    display: flex;
    align-items: center;
    padding: 0 10px;
    text-transform: uppercase;
  }

  .nav-item:hover, .nav-icon:hover {
    border-bottom: 2px solid white;
  }
</style>