<script>
  import { fade } from 'svelte/transition'

  export let work
  export let handleClose
</script>

<div id='work-details' in:fade={{ duration: 300 }}>
  <button class='mobile-only' on:click={handleClose}>X</button>
  <h2>{work.name}</h2>
  <iframe src={work.video} frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
  <p>{work.blurb}</p>
  <p class='quote'>"{work.quote}" -{work.quoteSrc}</p>

  <div id='links'>
    {#each work.links as link}
      <span><a href={link.url} class='work-link' target='blank'>{link.name}</a></span>
    {/each}
  </div>

  {#if work.name === 'Floodstream'}
    <div id='awards'>
      <div class='award-wrapper'>
        <a href='www.smushgallery.com'>
          <img class='award-image' src='https://erinkmcnulty.files.wordpress.com/2021/02/officialselection-essenceofembodiment-2021.png?w=1024' />
        </a>
      </div>
      <div class='award-wrapper'>
        <a href='https://www.sanjac.edu/programs-courses/areas-study/arts-humanities-communications-design/dance/dance-san-jac/artists-hope-international-dance-film-festival'>
          <img class='award-image' src='https://erinkmcnulty.files.wordpress.com/2021/02/official-selection-artists-for-hope-dance-film-festival-2021.png?w=1024' />
        </a>
      </div>
      <div class='award-wrapper'>
        <a href='https://praguefilmfest.com'>
          <img class='award-image' src='https://erinkmcnulty.files.wordpress.com/2021/02/finalist-prague-international-monthly-film-festival-2021.png?w=1024' />
        </a>
      </div>
    </div>
  {/if}
</div>

<style>
  #work-details {
    flex: 1;
  }

  iframe {
    width: 640px;
    height: 360px;
  }

  #links {
    display: flex;
    flex-direction: column;
  }

  #awards {
    display: flex;
  }

  .quote {
    font-style: italic;
  }

  .award-wrapper {
    padding: 1rem;
  }

  .award-image {
    width: 100%;
    height: auto;
  }

  .work-link {
    font-size: .9rem;
    color: black;
    display: inline;
    text-decoration: underline;
  }

  button {
    background-color: transparent;
    outline: none;
    border: none;
    padding: 0;
    margin: 0;
    text-align: left;
    margin-bottom: 1rem;
    position: absolute;
    top: 0;
    right: 0;
    padding: 1rem;
  }

  h2 {
    margin-bottom: 1rem;
  }

  @media (max-width: 600px) {
    #work-details {
      position: absolute;
      top: 72px;
      left: 0;
      height: 100%;
      width: 100%;
      background-color: white;
      padding: 2rem;
    }

    iframe {
      width: calc(100vw - 4rem);
      height: calc(56.25vw - 4rem);
    }

    #awards {
      flex-direction: column;
    }
  }
</style>