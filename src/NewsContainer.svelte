<script>
  import ReleaseNews from "./ReleaseNews.svelte";

</script>


<div id='news-container'>
  <ReleaseNews
    title='Upcoming'
    headline='New single "Close" comes out April 30'
    img='https://i.imgur.com/EDayasa.png'
    ctas={[
      {
        text: 'Listen on Spotify',
        link: 'https://open.spotify.com/album/5FvV8KnwRkMFm8LBGAiaRF?si=Imc_EGCxTOSk8NS2FSn9Gg'
      },
      {
        text: 'Listen on Apple',
        link: 'https://apple.co/30U8Gh0'
      },
      {
        text: 'Purchase on Vinyl',
        link: 'https://bit.ly/3gbcAs0'
      }
    ]}
  />
  <div id='spacer' />
  <ReleaseNews
    title='Recent Release'
    headline='Orchestral EP "A Step Back From the Wrong Direction" now streaming everywhere:'
    img='https://m.media-amazon.com/images/I/81CPa5sESkL._SS500_.jpg'
    ctas={[
      {
        text: 'Listen on Spotify',
        link: 'https://open.spotify.com/album/5FvV8KnwRkMFm8LBGAiaRF?si=Imc_EGCxTOSk8NS2FSn9Gg'
      },
      {
        text: 'Listen on Apple',
        link: 'https://apple.co/30U8Gh0'
      },
      {
        text: 'Purchase on Vinyl',
        link: 'https://bit.ly/3gbcAs0'
      }
    ]}
  />

  
</div>

<style>
  #news-container {
    background-color: rgba(0, 0, 0, 0.7);
    position: absolute;
    padding: 15px;
    width: 400px;
    min-height: 220px;
    max-height: 100%;
    top: 3rem;
    right: 3rem;
    color: white;
    text-overflow: clip;
    transition: 0.3s ease all;
  }

  #spacer {
    height: 2rem;
  }
</style>