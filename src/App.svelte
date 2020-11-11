<script>
	import {fade, slide} from "svelte/transition";
	import Button from "./modules/Bouton.svelte";
	let total = 0;

	function ajouter(nombre) {
		total += nombre;
	}

	$: carré = total * total;
</script>

<style>
</style>

<main transition:fade={{duration: 1000}}>
	<h1>{total}</h1>
	<p>Le carré est {carré}</p>
	{#if carré > 2500}
		<div class="turfu" transition:slide>Futur salaire ? ;) 🍾</div>
	{/if}

	<Button
		on:click={() => {
			ajouter(1);
		}}>
		AJOUTER 1
	</Button>

	<Button
		on:click={() => {
			ajouter(10);
		}}>
		AJOUTER 10
	</Button>
</main>
