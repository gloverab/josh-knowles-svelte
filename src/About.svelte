<script>
  import AboutText from './AboutText.svelte'
</script>

<div id='about-wrapper'>
  <div id='img-wrap'>
    <img src='https://i.imgur.com/1itLFSG.jpg' />
  </div>
  <div id='text-wrap'>
    <AboutText />
  </div>
</div>

<style>
  #about-wrapper {
		display: flex;
    height: 100%;
	}

	#about-wrapper #img-wrap {
    height: 100%;
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
      /* background-attachment: fixed; */
    }

    img {
      display: none;
    }
  }
</style>