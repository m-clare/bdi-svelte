<script>
	import AppBar from 'smelte/src/components/AppBar';
  import { Spacer } from 'smelte/src/components/Util';
	import IconButton from '$lib/IconButton.svelte';
  import TextButton from '$lib/TextButton.svelte';
	import FaButton from '$lib/FaButton.svelte';
	import { faGithub } from '@fortawesome/free-brands-svg-icons';

</script>

<AppBar
	classes="fixed top-0 w-screen items-center flex-wrap flex left-0 z-30 p-0 elevation-0 bg-dark-500 opacity-98"
>
	<div class="w-4" style="height: 52px" />
	<IconButton icon="menu" />
	<Spacer />
	<div style="width: 6px;" />
	<a href="/about" class="flex items-center">
    <TextButton text="About" />
  <div style="width: 12px;" />
	<a href="/" class="flex items-center">
    <TextButton text="Contact" />
	</a>
	<div style="width: 6px;" />
	<a href="/" class="flex items-center">
		<FaButton icon={faGithub} />
	</a>
	<div class="w-4" style="height:52px" />
</AppBar>
<div style="height: 52px;" />
