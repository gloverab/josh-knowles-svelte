<script>
  import { fade } from 'svelte/transition'
</script>

<svelte:head>
  <title>Josh Knowles | Contact and Booking</title>
</svelte:head>

<div in:fade={{ delay: 200, duration: 300 }}>
  <h1>Contact</h1>
  <p class='thin'>I'm currently available for film scoring, session work, live performances, and open to working on any type of project. Please feel free to get in touch!</p>

  <p class='thin'>For projects or bookings&nbsp;<a href='mailto:jaknowles320@gmail.com'>Send me an Email</a></p>

  <p class='thin'>Follow me on:</p>
  <p class='link'><a href='https://www.instagram.com/joshknowlesmusic'>Instagram</a></p>
  <p class='link'><a href='https://www.facebook.com/joshknowlesmusic'>Facebook</a></p>
  <p class='link'><a href='https://www.youtube.com/@joshknowles9440'>Youtube</a></p>
</div>

<style>
  p {
    line-height: 1;
  }

  p.thin {
    font-weight: 300;
  }

  p.thin a {
    font-weight: 800;
  }

  p.link {
    line-height: 0.5;
  }

  h1 {
    font-size: 1.5rem;
    text-transform: uppercase;
    font-weight: 300;
  }

  a {
    color: white;

  }

  a:hover {
    text-decoration: underline;
  }
</style>