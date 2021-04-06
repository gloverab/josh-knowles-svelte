<script>
  import WorkDetails from './WorkDetails.svelte'
  let activeWork = undefined


  const works = [
    {
      name: 'Floodstream',
      video: 'https://player.vimeo.com/video/467149757',
      blurb: `This is a sequence from the short film, RECK. To channel the anxiety of the drug-addicted mother looking for her child, I composed with heavily de-tuned strings, manipulated vocal inhales/exhales, and a distorted/pitch-shifted “bass” violin. `,
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
      blurb: `“A Step Back from the Wrong Direction” is a five-movement instrumental violin piece which I created at the beginning of the COVID-19 lockdown. Movement III (above) is a reflection on the feeling of isolation and yearning that was so prevalent to many during that period of time.`,
      quote: 'Josh Knowles offers New England the kind of music that makes the most sense today: a type of music meant for contemplation, discovery, and healing.',
      quoteSrc: 'Deli Mag',
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
      blurb: `Floodstream was a collaboration with dancer Erin Mcnulty, and premiered as part of the Shawna Shea Film Festival’s ‘Spring Into Fall’ Shorts Fest. Erin sent me the finished cut with no music set to it. I developed the score around the visuals using electric violin coupled with various pitch modulation, delay and looping techniques.`,
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
      blurb: `“Same” is an original song. For the music video, I collaborated with Boston Ballet principal dancers Paul Craig and Lia Cirio. Yury Yanowsky, a former Boston Ballet principal dancer and artistic director of Festival Ballet Providence, created the choreography for the piece. `,
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