<script>
	let value = "default";
	let isInside;

	function handleMouseOver() {
		isInside = true;
	}

	function handleMouseOut() {
		isInside = false;
	}
</script>


<div>
	<h2>Svelte bindings</h2>
	<p>
		On svelte, the data bindings allow to bi-directionally attach the value of a variable with one or more components.
	</p>

	<p>A very simple example would be a text input that binds it's value to a variable:</p>
	<input type="text" bind:value={value}>
	<p>The binded value is {value}</p>

	<p>
		<b>NOTE:</b> Data bindings can be applied to different properties. Just to name a few examples:
	</p>

	<ul>
		<li>You can make a data binding on the `checked` prop in checkboxes</li>
		<li>Also the `value` prop on select boxes can be bound.</li>
		<li>Audio and Video media tags can be bound on `currentTime`, `duration`, `paused`, etc. </li>
	</ul>

	<a href="https://flaviocopes.com/svelte-bindings/">More useful details on Svelte bindings</a>
</div>
<hr>
<div>
	<h2>Event handling</h2>
	<p>Svelte allows to attach a function to any event</p>

	<div class="hoverable-box" on:mouseover={handleMouseOver} on:mouseout={handleMouseOut}>
		{isInside ? "😃😃 YAAAY!!😃😃" : "Hover me"}
	</div>

	<p><b>NOTE:</b> You can pass event handlers as props to children components.</p>
</div>

<style>
	.hoverable-box {
		background-color: black;
		color: white;
		width: 100%;
		height: 200px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 32px;
	}

	.red {
		color: red;
	}

	.green {
		color: green;
	}
</style>