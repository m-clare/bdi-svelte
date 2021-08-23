<script>
	import Button from 'smelte/src/components/Button';

  export let value = false;
	export let text = null;
	export let color = null;
	export let textClass = 'flex items-center select-none p-2';
</script>

<div on:mouseleave>
	<Button
		flat
		text
		{color}
		{textClass}
		add={color ? color : 'dark:text-white text-primary-a700'}
		remove="py-2 px-4 p-4"
		on:click={() => value != value}
		on:click
		on:mouseover
		on:*
	>
		{text}
	</Button>
</div>
