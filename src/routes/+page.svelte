<script>
	import { onMount } from 'svelte';
	import { Playerjs } from './playerjs';
	let player;
	onMount(() => {
		player = new Playerjs({
			id: 'player',
			file: `https://pixeldrain.com/api/file/7X1Gvu3B`,
			title: `test video`,
		});


		window.PlayerjsMenu2 = function (id, title, item) {
			if (item === 0) {
				pljssglobal[0].api('design', 1);
			}

			if (item === 1) {
				pljssglobal[0].api('design', 2);
			}
		}; 
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
