<script>
  import { fade } from 'svelte/transition'
</script>

<div in:fade={{ delay: 200, duration: 300 }}>
  <h2>Contact</h2>
  <p>I'm currently available for film scoring, session work, live performances, and open to working on any type of project. Please feel free to get in touch!</p>

  <p><a href='mailto:jaknowles320@gmail.com'>Click here to Email me</a></p>
  <p><a href='www.instagram.com/joshknowlesmusic'>Instagram</a></p>
  <p><a href='www.facebook.com/joshknowlesmusic'>Facebook</a></p>
</div>

<style>
  h2 {
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