<script>
  import WorkDetails from './WorkDetails.svelte'
  let activeWork = undefined

  let loadingWork = false

  const works = [
    {
      name: 'Reck',
      year: '(upcoming)',
      type: 'Short film score',
      video: 'https://www.youtube.com/embed/_ZtSRTYGyVE',
      blurb: `This is a sequence from the short film, RECK. To channel the anxiety of the drug-addicted mother looking for her child, I composed with heavily de-tuned strings, manipulated vocal inhales/exhales, and a distorted/pitch-shifted “bass” violin. `,
      quote: 'Reck is an upcoming short film - this snippet is for private viewing only, please do not share.',
      links: []
    },
    {
      name: 'Floodstream',
      year: '(2020)',
      type: 'Dance film score',
      video: 'https://www.youtube.com/embed/61OtHgZp3Bk',
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
      name: 'A Step Back from the Wrong Direction',
      year: '(2020)',
      type: 'Original work / neo-classical composition',
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
      name: 'Same',
      year: '(2018)',
      type: 'Original work / songwriting',
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

  const setActive = (workNum) => {
    loadingWork = true
    activeWork = workNum
    setTimeout(() => loadingWork = false, 10)
  }
</script>

<svelte:head>
  <title>Josh Knowles Music | Selected Works</title>
</svelte:head>

<div id='selected-works-wrapper'>
  <div id='works-list'>
    <h1>Selected Works</h1>

    {#each works as workButton, i}
      <button on:click={() => setActive(i)} class:selected={activeWork === i}>
        <h3>{workButton.name} {workButton.year}</h3>
        <span>{workButton.type}</span>
      </button>
    {/each}

  </div>
  

  {#if activeWork !== undefined}
    <WorkDetails
      loadingWork={loadingWork}
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

  #work-wrapper {
    flex: 1;
  }

  button {
    background-color: transparent;
    outline: none;
    border: none;
    padding: 0;
    margin: 0;
    text-align: left;
    margin-bottom: 1rem;
    position: relative;
  }

  button:hover {
    cursor: pointer;
  }

  button:active {
    color: black;
    background-color: transparent;
  }

  button:after {
    content: '';
    position: absolute;
    bottom: 0;
    left: -2px;
    width: 90%;
    height: 1px;
    background: linear-gradient(90deg, rgba(0,0,0,1) 54%, rgba(86,118,125,0) 100%);
    transform: scale3d(0,1,1);
    transition: .2s ease all;
    transform-origin: left;
  }

  button:hover:after {
    transform: scale3d(.1,1,1);
  }

  button.selected:after {
    transform: scale3d(1,1,1);
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
  
  h1 {
    text-transform: uppercase;
    font-size: 1.5rem;
    font-weight: 300;
    margin-bottom: 2rem;
  }

  @media (max-width: 600px) {
    #selected-works-wrapper {
      flex-direction: column;
    }
  }
</style>