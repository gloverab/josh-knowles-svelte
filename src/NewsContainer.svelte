<script>
  import { fade } from 'svelte/transition'
  import ReleaseNews from "./ReleaseNews.svelte";

</script>

<div in:fade={{ delay: 200, duration: 300 }}>
  <ReleaseNews
    title='Out Now'
    headline='New single "Pattern" out everywhere 5/12'
    img='https://www.dropbox.com/s/uz4wsq0n0e5nnii/pattern-3000x3000.jpeg?raw=1'
    ctas={[
      {
        text: 'Listen on Spotify',
        link: 'https://open.spotify.com/artist/2cYJgCe7KbXn1Y4TL0JCrK?si=R5WOBLLNRnGx2rSTtB-uRQ'
      },
      {
        text: 'Listen on Apple Music',
        link: 'https://music.apple.com/us/artist/josh-knowles/635148421'
      },
      {
        text: 'Listen on Bandcamp',
        link: 'https://joshknowles.bandcamp.com'
      }
    ]}
  />
  <div id='spacer' />
  <ReleaseNews
    title='Recent Release'
    headline='New Single "Night and Day" now streaming everywhere:'
    img='https://www.dropbox.com/s/d8uoxim7lnjiqmy/night-and-day-3000x3000.jpeg?raw=1'
    ctas={[
      {
        text: 'Listen on Spotify',
        link: 'https://open.spotify.com/track/6JzqP1vgB1JxdTspjO3Sbw?si=a86c1a1e7cb94ee2'
      },
      {
        text: 'Listen on Apple',
        link: 'https://music.apple.com/us/album/night-and-day/1656454471?i=1656454472&app=itunes'
      },
      {
        text: 'Listen on Bandcamp',
        link: 'https://joshknowles.bandcamp.com/track/night-and-day'
      }
    ]}
  />
</div>

<style>
  #spacer {
    height: 2rem;
  }
</style>