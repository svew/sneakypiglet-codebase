<script>
    import OptionalCheck from "../OptionalCheck.svelte";

    export let title;
    export let content;
    export let optional;
</script>

<OptionalCheck {optional} {content}>
    {#if title}
        <b>{@html title}</b>
    {/if}
    <p>
        {@html content.replaceAll("\n", "<br/>")}
    </p>
</OptionalCheck>

<style>
	p {
		margin-bottom: 0px;
		margin-left: 24px;
		padding-bottom: 8px;
	}
</style>