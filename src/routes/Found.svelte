<script lang="ts">
	import { receive } from './transitions';

	export let found: string[];
</script>

<div class="found">
	{#each found as emoji}
		<div class="pair">
			<span in:receive={{ key: `${emoji}:a` }}>{emoji}</span>
			<span in:receive={{ key: `${emoji}:b` }}>{emoji}</span>
		</div>
	{/each}
</div>

<style>
	span {
		font-size: 4em;
	}
	.found {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 0.5em;
		height: 100%;
		filter: drop-shadow(0.2em 0.2em 0.5em rgba(0, 0, 0, 0.2));
	}

	.pair {
        display: flex;
        justify-content: center;
        align-items: center;
		width: 6em;
		height: 6em;
		background: white;
		padding: 3em;
        border-radius: 50%;
	}

	span {
		position: absolute;
    
	}
</style>
