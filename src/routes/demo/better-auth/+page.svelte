<script lang="ts">
	import { enhance } from '$app/forms';
	import type { PageServerData } from './$types';

	let { data }: { data: PageServerData } = $props();
</script>

<h1>Bienvenue, {data.user.name}!</h1>
<p>Votre ID Utilisateur est : {data.user.id}.</p>
<form method="post" action="?/signOut" use:enhance>
	<button>Se déconnecter</button>
</form>

<style>
	:global(body) {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		font-family: sans-serif;
		margin: 0;
	}

	h1 {
		color: #f0eeff;
		font-size: 2rem;
		margin: 0 0 0.5rem;
	}

	p {
		color: #8e88b0;
		margin: 0 0 1.5rem;
	}

	button {
		background: transparent;
		color: #7c6af7;
		border: 1.5px solid #7c6af7;
		border-radius: 8px;
		padding: 0.6rem 1.5rem;
		font-size: 0.9rem;
		cursor: pointer;
	}

	button:hover {
		background: rgba(124, 106, 247, 0.1);
	}
</style>
