<script>
	import { onMount } from 'svelte'
	import router, { curRoute } from './router.js'
	import Header from "./Header.svelte";
	import About from "./About.svelte";
	import Press from "./Press.svelte";
	import Contact from "./Contact.svelte";
	import SelectedWorks from "./SelectedWorks.svelte";
	import NewsContainer from "./NewsContainer.svelte";

	export let name;

	onMount(() => {
		curRoute.set(window.location.pathname);
		if (!history.state) {
			window.history.replaceState({path: window.location.pathname}, '',   window.location.href)
		}
	})

	function handlerBackNavigation(event){
		curRoute.set(event.state.path)
	}
</script>

<svelte:window on:popstate={handlerBackNavigation} />

<main>
	<Header />

	{#if $curRoute.includes('selected-works')}
		<SelectedWorks />
	{:else}
		{#if $curRoute.includes('press')}
			<Press />
		{:else}
			<div id='background-image'>
				<div id='site-content'>
					<div id='content-container' class={$curRoute.replace('/', '')}>
						{#if $curRoute.includes('about')}
							<About />
						{:else if $curRoute.includes('contact')}
							<Contact />
						{:else}
							<NewsContainer />
						{/if}
					</div>
				</div>
			</div>
		{/if}
	{/if}

</main>

<style>
	#background-image {
		width: 100vw;
		height: calc(100vh - 72px);
		position: absolute;
		bottom: 0;
		left: 0;
		background-image: url('https://i.imgur.com/3ttb9Jb.jpg');
		background-position: center;
		background-repeat: no-repeat;
		background-size: cover;
		background-attachment: fixed;
	}

	#site-content {
		width: 100%;
		max-width: 1400px;
		height: calc(100vh - 72px);
		position: absolute;
		display: flex;
		justify-content: flex-end;
		bottom: 0;
		left: 0;
		padding: 3rem;
	}

	#content-container {
    background-color: rgba(0, 0, 0, 0.7);
    position: relative;
    padding: 15px;
    width: 400px;
		height: 600px;
    min-height: 220px;
    max-height: 100%;
    top: 0;
    right: 0;
    color: white;
    text-overflow: clip;
    transition: 0.3s ease all;
  }

	#content-container.about {
		width: 100%;
		height: 100%;
	}

	#content-container.contact {
		width: 400px;
		height: 400px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>