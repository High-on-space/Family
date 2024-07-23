<script>
	import { onMount } from "svelte";
	import { fly } from 'svelte/transition'
	import { fade } from 'svelte/transition'
	let begin=false
</script>

<div class='container'>
	{#if !begin}
		<button class='start' on:click = {() => begin=!begin} transition:fade>
			Bắt đầu
		</button>
	{:else}
		<div class='bar' transition:fly={{duration:1500, x:-200}}>

		</div>
	{/if}
</div>

<style>
	.container
	{
		width: 100vw;
		height: 100vh;
		max-width: 100%;
		display: flex;
		justify-content: center;
	}
	.start
	{
		padding:0;
		margin-top:75vh;
		margin-bottom:15vh;
		width: 200px;
	}
	.bar
	{
		width:20vw;
		height: 100vh;
		max-width: 100%;
		position: absolute;
		background-color: red;
		left:0
	}
	
</style>