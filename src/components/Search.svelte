<script>
	export let value = "";
</script>

<input class="search-box" type="search" bind:value>

<style>
	.search-box {
		display: flex;
		flex-direction: row-reverse;
		border: 1px solid #d1d5db;
		box-sizing: border-box;
		margin-bottom: 8px;
		padding: 6.4px;
	}
</style>