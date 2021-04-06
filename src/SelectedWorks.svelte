<script>
  import WorkDetails from './WorkDetails.svelte'
  let activeWork = undefined


  const works = [
    {
      name: 'Floodstream',
      video: 'https://player.vimeo.com/video/467149757',
      blurb: `Floodstream was a collaboration with dancer Erin Mcnulty, and premiered as part of the Shawna Shea Film Festival’s ‘Spring Into Fall’ Shorts Fest.`,
      quote: 'Knowles’ experimental mixing techniques with his violin, builds a sense of sadness. There’s also somehow hope — a sense that supports the dancers’ movement and presence. All together, it’s a captivating presentation, creating both food for thought and aesthetic wonder.',
      quoteSrc: 'Dance Informa',
      links: [
        {
          name: `Feature on Dance Informa`,
          url: 'https://www.danceinforma.com/2020/10/16/floodstream-in-the-shawna-shea-film-festival-shorts-fest-dancing-to-commemorate/'
        },
        {
          name: 'Floodstream',
          url: 'https://erinkmcnulty.com/projects/floodstream/'
        }
      ]
    },
    {
      name: 'A Step Back from the Wrong Direction',
      video: 'https://www.youtube.com/embed/v7L5DC5WSL4',
      quote: 'Josh Knowles offers New England the kind of music that makes the most sense today: a type of music meant for contemplation, discovery, and healing.',
      blurb: `A Step Back From the Wrong Direction is a 5-movement neo-classical piece`,
      links: [
        {
          name: `Premiere on Deli Mag`,
          url: 'http://m-ne.thedelimagazine.com/43477/deli-premiere-step-back-from-wrong-direction-by-josh-knowles'
        },
        {
          name: 'Spotify',
          url: 'https://open.spotify.com/album/5FvV8KnwRkMFm8LBGAiaRF?si=Imc_EGCxTOSk8NS2FSn9Gg'
        },
        {
          name: 'Apple/iTunes',
          url: 'https://apple.co/30U8Gh0'
        },
        {
          name: 'Vinyl',
          url: 'https://joshknowles.bandcamp.com/track/a-step-back-from-the-wrong-direction-i-2'
        }
      ]
    },
    {
      name: 'Floodstream',
      video: 'https://player.vimeo.com/video/467149757',
      blurb: `Floodstream was a collaboration with dancer Erin Mcnulty, and premiered as part of the Shawna Shea Film Festival’s ‘Spring Into Fall’ Shorts Fest.`,
      quote: 'Knowles’ experimental mixing techniques with his violin, builds a sense of sadness. There’s also somehow hope — a sense that supports the dancers’ movement and presence. All together, it’s a captivating presentation, creating both food for thought and aesthetic wonder.',
      quoteSrc: 'Dance Informa',
      links: [
        {
          name: `Feature on Dance Informa`,
          url: 'https://www.danceinforma.com/2020/10/16/floodstream-in-the-shawna-shea-film-festival-shorts-fest-dancing-to-commemorate/'
        },
        {
          name: 'Floodstream',
          url: 'https://erinkmcnulty.com/projects/floodstream/'
        }
      ]
    },
    {
      name: 'Same',
      video: 'https://www.youtube.com/embed/_drI0UGkKZg',
      blurb: `Same is an original song, etc`,
      quote: "...a gorgeously haunting pas de deux",
      quoteSrc: 'Pointe Mag',
      links: [
        {
          name: `Pointe Mag Premiere`,
          url: 'https://www.pointemagazine.com/dont-miss-boston-ballets-lia-cirio-and-paul-craig-in-this-new-music-video-2635415909.html'
        },
        {
          name: 'Spotify',
          url: 'https://open.spotify.com/track/1yEnmru0YziioqclSpLsDe?si=eiMCfJubRdCBwVcmlmwRYA'
        },
        {
          name: 'Apple/iTunes',
          url: 'https://music.apple.com/us/album/same-single/1459414420'
        }
      ]
    },
  ]
</script>

<div id='selected-works-wrapper'>
  <div id='works-list'>
    <h2>Selected Works</h2>

    <button on:click={() => activeWork = 0}>
      <h3>Reck (2020)</h3>
      <span>Short film scoring</span>
    </button>

    <button on:click={() => activeWork = 1}>
      <h3>A Step Back from the Wrong Direction (2020)</h3>
      <span>Neo-classical composition</span>
    </button>

    <button on:click={() => activeWork = 2}>
      <h3>Floodstream (2019)</h3>
      <span>Dance film scoring</span>
    </button>
    
    <button on:click={() => activeWork = 3}>
      <h3>Same (2018)</h3>
      <span>Original work / songwriting</span>
    </button>
  </div>
  
  {#if activeWork}
    <WorkDetails
      work={works[activeWork]}
      handleClose={() => activeWork = undefined}
    />
  {/if}
</div>

<style>
  #works-list {
    display: flex;
    flex: 1;
    flex-direction: column;
  }

  button {
    background-color: transparent;
    outline: none;
    border: none;
    padding: 0;
    margin: 0;
    text-align: left;
    margin-bottom: 1rem;
  }

  button:hover {
    cursor: pointer;
  }

  span {
    font-style: italic;
  }

  #selected-works-wrapper {
    max-width: 1400px;
    padding: 2rem;
    display: flex;
    justify-content: space-between;
  }
  
  h2 {
    /* text-transform: uppercase; */
    font-weight: 300;
    margin-bottom: 2rem;
  }

  @media (max-width: 600px) {
    #selected-works-wrapper {
      flex-direction: column;
    }
  }
</style>