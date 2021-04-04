<script>
	// This works as a wrapper to test the lifecycle of Svelte components
	import Time from './components/Time.svelte';

	let isMounted = false;

	function toggleMount() {
		isMounted = !isMounted;
	}
</script>

<div>
	<div>
		The button bellow is a test of the lifecycle on Svelte components. It is recommended to see you console at your browser's dev tools.
	</div>
	<button on:click={toggleMount}>{isMounted ? 'Hide' : 'Show'} time</button>

	{#if isMounted}
		<Time />
	{/if}
</div>



