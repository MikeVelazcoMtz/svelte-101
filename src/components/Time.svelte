<script>
	import { onMount, onDestroy } from "svelte";
	let interval = null;
	let time = "loading...";

	function tick() {
		time = new Date().toLocaleTimeString();
	}

	onMount(() => {
		console.log("mounting...");
		interval = setInterval(tick, 1000);
	});

	onDestroy(() => {
		console.log("unmounting...");
		clearInterval(interval);
	});
</script>

<p>Hello user, it's {time}</p>
