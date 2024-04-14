<script>
	import { onMount } from 'svelte';
	import { Playerjs } from './playerjs';
	import SubtitleOctopus from 'libass-wasm';
	let player;
	let subtitleOctopus;

	onMount(() => {
		player = new Playerjs({
			id: 'player',
			file: `https://pixeldrain.com/api/file/7X1Gvu3B`,
			title: `test video`,
			default_quality: '1080p',
			thumbnails: 'https://pixeldrain.com/api/file/ZizkyAZB',
			points:[{time:10, width:"90s", opacity:1, color:"#000000", text:"Description"},{time:33}],
			rec: [
				{
					title: 'Metallic Rouge - 03',
					poster: 'https://pixeldrain.com/api/file/Q5qJr1HK',
					link: 'http://localhost:5173/anime/Metallic_Rouge/3/watch'
				},
				{
					title: 'Metallic Rouge - 04',
					poster: 'https://pixeldrain.com/api/file/KeZXEWXa',
					link: 'http://localhost:5173/anime/Metallic_Rouge/4/watch'
				}
			]
		});
		document.getElementById('player').addEventListener('init', playerInit);
	});

	function playerInit() {
		let video = document.querySelector(`[src="https://pixeldrain.com/api/file/7X1Gvu3B"]`);
		console.log(video)
		var options = {
			video: video, // HTML5 video element
			subUrl: 'https://pixeldrain.com/api/file/vKALavtx', // Link to subtitles
			workerUrl: '/subtitles-octopus-worker.js', // Link to WebAssembly-based file "libassjs-worker.js"
			legacyWorkerUrl: '/subtitles-octopus-worker-legacy.js',
			debug: true,
			renderMode: 'wasm-blend',
			fallbackFont: 'https://pixeldrain.com/api/file/ghmx7kuj'
		};
		subtitleOctopus = new SubtitleOctopus(options);
	}
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
