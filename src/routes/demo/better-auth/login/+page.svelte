<script lang="ts">
	import { enhance } from '$app/forms';
	import type { ActionData } from './$types';

	let { form }: { form: ActionData } = $props();
</script>

<div class="form">
	<form method="post" action="?/signInEmail" class="form-content" use:enhance>
		<h1>Créer un compte</h1>
		<input name="name" class="ep" placeholder="Nom" />
		<input type="email" name="email" placeholder="Email" class="ep" />

		<input
			type="password"
			name="password"
			placeholder="Entrez votre mot de passe"
			minlength="12"
			class="ep"
		/>

		<button>S'identifier</button>
		<button formaction="?/signUpEmail">Inscription</button>
	</form>
	<p style="color: red">{form?.message ?? ''}</p>
</div>

<p style="color: red">{form?.message ?? ''}</p>

<style>
	.form {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background: #1a1828;
		font-family: sans-serif;
	}

	h1 {
		color: #f0eeff;
		font-size: 1.8rem;
		margin: 0 0 1.5rem;
	}

	.form-content {
		background: #231f35;
		border-radius: 16px;
		padding: 2rem;
		width: 100%;
		max-width: 380px;
		display: flex;
		flex-direction: column;
		gap: 0.75rem;
	}

	.ep {
		width: 100%;
		background: #2c2842;
		border: 1.5px solid #3a3456;
		border-radius: 8px;
		padding: 0.75rem 1rem;
		color: #f0eeff;
		font-size: 0.9rem;
		outline: none;
		box-sizing: border-box;
	}

	.ep:focus {
		border-color: #7c6af7;
	}
	.ep::placeholder {
		color: #8e88b0;
	}

	button {
		width: 100%;
		border: none;
		border-radius: 8px;
		padding: 0.85rem;
		font-size: 0.95rem;
		cursor: pointer;
	}

	button:first-of-type {
		background: #7c6af7;
		color: #fff;
	}

	button:first-of-type:hover {
		background: #6a57e8;
	}

	button:last-of-type {
		background: transparent;
		color: #7c6af7;
		border: 1.5px solid #7c6af7;
	}

	button:last-of-type:hover {
		background: rgba(124, 106, 247, 0.1);
	}
</style>
