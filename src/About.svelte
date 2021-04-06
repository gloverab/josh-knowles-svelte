<script>
  import { fade } from 'svelte/transition'
  import AboutText from './AboutText.svelte'
</script>

<div id='container' in:fade={{ delay: 200, duration: 300 }}>
  <div id='about-wrapper'>
    <div id='img-wrap'>
      <img src='https://i.imgur.com/1itLFSG.jpg' />
    </div>
    <div id='text-wrap'>
      <h2>Josh Knowles</h2>
      <h4>Boston, MA</h4>
      <h4 id='blurby'>Violinist / Composer / Songwriter / Singer</h4>
      <div class='desktop-only'>
        <AboutText />
      </div>
    </div>
  </div>
  <div class='mobile-only'>
    <AboutText />
  </div>
</div>

<style>
  #container {
    height: 100%;
  }

  #about-wrapper {
		display: flex;
    height: 100%;
	}

	#about-wrapper #img-wrap {
    height: 100%;
	}

  h4 {
    font-weight: 300;
  }

  img {
    height: 100%;
  }

	#about-wrapper #text-wrap {
		flex: 1;
		padding-left: 1rem;
	}

  @media only screen and (max-width: 1000px) {
    #about-wrapper #img-wrap {
      flex: 1;
      height: 100%;
      background: url('https://i.imgur.com/1itLFSG.jpg');
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
    }

    img {
      display: none;
    }
  }

  @media (max-width: 600px) {
    #about-wrapper {
      height: auto;
    }

    #about-wrapper #img-wrap {
      background: none;
    }

    img {
      width: 100%;
      height: auto;
      display: block;
    }
  }
</style>