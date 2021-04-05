<script>
	import { onMount } from 'svelte'
	import router, { curRoute } from './router.js'
	import Header from "./Header.svelte";
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
	<div id='background-image'>
		<div id='site-content'>
			{#if (!$curRoute.includes('about'))}
				<NewsContainer />
			{/if}
		</div>
	</div>

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
		height: calc(100vh - 72px);
		position: absolute;
		bottom: 0;
		left: 0;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>