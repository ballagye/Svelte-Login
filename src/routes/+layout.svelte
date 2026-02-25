<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}

<style>
	:global {
		@import url('https://fonts.cdnfonts.com/css/sf-pro-display');
		* {
			font-family: 'SF Pro Display', sans-serif;
			margin: 0px;
			padding: 0px;
		}
	}
	:global(body) {
		background-color: #2c2638;
		color: white;
	}
	:global(input) {
		font-family: 'SF Pro Display', sans-serif;
	}
</style>
