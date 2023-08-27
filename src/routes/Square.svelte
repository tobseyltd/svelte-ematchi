<script lang="ts">
	export let emoji: string;
	export let selected: boolean;
</script>

<div class="square" class:flipped={selected}>
	<button on:click></button>
	<span>{emoji}</span>
</div>

<style>
	.square {
		display: flex;
		justify-content: center;
		align-items: center;
		background: yellow;
	}

	span {
		font-size: 5em;
		pointer-events: none;
	}

	button {
		position: absolute;
		height: 100%;
		width: 100%;
	}

	.flipped button {
		background: red;
	}
</style>
