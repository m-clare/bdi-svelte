<script>
	import Header from '$lib/Header/index.svelte';
	import '../app.css';
	import { navMenu } from '../utils/menu.js';
	import List, { ListItem } from 'smelte/src/components/List';
	import NavigationDrawer from 'smelte/src/components/NavigationDrawer';
import { page } from '$app/stores';

  $: path = $page.path;
</script>

<Header />

{#each navMenu as link}
	<a href={link.to} class="hidden">{link.text}</a>
{/each}

<main class="relative p-8 lg:max-w-3xl mx-auto mb-10 mt-24 md:ml-64 md: pl-16">
	<NavigationDrawer elevation={true}>
		<h4
			class="px-3 ml-1 pb-2 pt-8 text-lg text-gray-900 font-light
    dark:text-gray-100"
		>
			Visualizations
		</h4>
		<List items={navMenu}>
			<span slot="item" let:item class="cursor-pointer">
				<a href={item.to}>
					<ListItem
						id={item.id}
						text={item.text}
						to={item.to}
						selected={path.includes(item.to)}
						dense
						selectedClasses="bg-primary-transDark dark:bg-primary-transLight
      hover:bg-primary-transDark dark-hover:bg-primary-transLight"
					/>
				</a>
			</span>
		</List>
	</NavigationDrawer>
	<slot />
</main>

<footer>
	<p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
