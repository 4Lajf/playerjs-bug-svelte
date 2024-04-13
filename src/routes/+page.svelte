<script>
	import { onMount } from 'svelte';
	import { Playerjs } from './playerjs';
	let player;

	onMount(() => {
		player = new Playerjs({
			id: 'player',
			file: `https://pixeldrain.com/api/file/7X1Gvu3B`,
			poster: 'https://pixeldrain.com/api/file/FUN6giYi',
			title: `test video`,
			default_quality: '1080p',
			thumbnails: 'https://pixeldrain.com/api/file/mdmPa81q',
			points: [{ time: 12 }, { time: 33 }],
		});
	});
</script>

	<div id="player" />

<style>
	@font-face {
		font-family: 'vt323';
		src: url('vt323-regular-webfont.woff2') format('woff2');
		font-weight: normal;
		font-style: normal;
	}
</style>
