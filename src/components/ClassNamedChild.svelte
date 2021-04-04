<script>
	export let classnames= "";
</script>

<p class="child {classnames}">
	Hello, I'm ClassyChild.
</p>

<style>
	.child {
		background-color: black;
		color: white;
	}

	.inverted {
		background-color: white;
		color: black;
	}
</style>