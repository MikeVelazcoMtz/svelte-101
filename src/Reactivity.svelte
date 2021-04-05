<script>
	let names = [
		'mike',
		'james',
		'rose',
		'kyle',
		'andrew',
		'john',
		'Kelly',
		'Brittany',
		'Beth',
		'Adrian'
	];

	

	// Every time `count` value changes, this variable value will change too
	$: shownNames = names.slice(0, count);

	let count = 10;

	function sum() {
		count = count + 1;
		// also count += 1 works, but count++ doesn't.
	}

	function substract() {
		if (count >= 1) {
			count -= 1;
		}
		// Only direct assignments affect the state of internal variables and props.
	}
</script>
<p>
	Svelte handles reactivity trough internal variables and props.
</p>
<p>
	The difference between internal variables and props in terms of the deffinition at code level is the `export` keyword.
</p>
<p>
	Anyways you can have props with default values, just in case the implemented component doesn't add any information about the prop value.
</p>

<input type="number" name="count" id="count" disabled value={count}> 
<div>
	<span>{count}</span> <button on:click={substract}>-</button> <button on:click={sum}>+</button>
</div>

<hr>

<p>In terms of the dynamic rendering and logic  we are allowed to use `if`, `else`, `elseif` statements and loops with `each` blocks</p>

<p>`each` implementation example: </p>

<ul>
	{#each shownNames as item, key }
		<li {key}>{item}</li>
	{:else}
		<p>No items to show</p>
	{/each}
</ul>

<p>
	`if ... else if ... else` implementation example:
</p>


{#if count === 0}
	{count} is zero.
{:else if count % 2 === 0}
	{count} is even.
{:else}
	{count} is odd.
{/if}
