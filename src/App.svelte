<script>
	import Search from './components/Search.svelte';
    import { onMount } from 'svelte';
	import yaml from 'js-yaml';
    import RecipeList from './components/RecipeList.svelte';
	
	let searchTerm = "";
	let recipes = [];

	onMount(fetch("Recipes.yml")
			.then(response => response.text())
			.then(responseText => recipes = yaml.load(responseText).recipes));
</script>

<h1>Michael's Drinks List</h1>
<Search bind:value={searchTerm}></Search>
<RecipeList {recipes} {searchTerm}/>