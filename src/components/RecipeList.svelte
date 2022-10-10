<script>
	import RecipeItem from './RecipeItem.svelte';
    
    export let recipes = [];
    export let searchTerm = "";

	function matchesSearch(recipe, term) {
		if (!term) {
			return true;
		}
		term = term.toLowerCase();
		if (recipe.name.toLowerCase().includes(term)) {
			return true;
		}
		for (let item of recipe.ingredients) {
			if (item.toLowerCase().includes(term)) {
				return true;
			}
		}
		return false;
	}
</script>

{#each recipes as recipe}
	{#if matchesSearch(recipe, searchTerm)}
		<RecipeItem {...recipe}></RecipeItem>
	{/if}
{/each}