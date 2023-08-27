<script lang="ts">
	import { send } from './transitions';

	export let emoji: string;
	export let selected: boolean;
	export let found: boolean;
	export let group: 'a' | 'b'
</script>

<div class="square" class:flipped={selected || found}>
	<button on:click />
	<div class="background" />

	{#if !found}
		<span out:send={{ key: `${emoji}:${group}` }}>{emoji}</span>
	{/if}
</div>

<style>
	.square {
		display: flex;
		justify-content: center;
		align-items: center;
		transform-style: preserve-3d;
		transition: transform 0.4s;
	}

	span {
		font-size: 5em;
		pointer-events: none;
		transform: rotateY(180deg);
		backface-visibility: hidden;
	}

	button {
		position: absolute;
		height: 100%;
		width: 100%;
		backface-visibility: hidden;
		background: #ccc;
		border: 0;
		border-radius: 1em;
		font-size: inherit;
	}

	.flipped {
		background: #eee;
		transform: rotateY(180deg);
	}

	.background {
		position: absolute;
		background: #eee;
		border: 0.5em solid #eee;
		transform: rotateY(180deg);
		backface-visibility: hidden;
		width: 100%;
		height: 100%;
		border-radius: 1em;
	}
</style>
