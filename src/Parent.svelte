<script>
	import Child from './components/Child.svelte';
	import ClassyChild from './components/ClassyChild.svelte';
	import ClassNamedChild from './components/ClassNamedChild.svelte';
	import ReferencedChild from './components/ReferencedChild.svelte';
</script>

<p>
	This is the parent component which contains a Child component below:
</p>

<Child />

<p>That child component has it's own styling that can't be overriden by default.</p>
<p>
	You have three alternatives to customize components:
</p>
<ul>
	<li>
		Passing specific style props as here:
		<br />
		<ClassyChild color="red" backgroundColor="blue" />
	</li>
	<li>
		Custimizing the component via classnames inside the component (my personal favorite so far):
		<br />
		<ClassNamedChild classnames="inverted" />
	</li>
	<li>
		Using reference and the `:global` selector and doing the customization in the parent (it might be required some times, but also keep the door open for some messy styling).
		<br />
		<ReferencedChild ref="green" />
	</li>
</ul>
<p>
	As you might notice on the `style` tag there is some CSS code that might affect all the child component, but it just doesn't because of Svelte's nature.
</p>


<style>
	.child {
		background-color: pink;
		color:blue;
	}

	:global([ref=green]) {
		background-color: orange;
		color: green;
	}
</style>
