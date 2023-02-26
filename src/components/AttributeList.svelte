<script>
    import AttributeItem from "./AttributeItem.svelte";
    export let attributes = [];
    
</script>

<div class="attr-list">
    {#each attributes as value, index (index)}
        <AttributeItem item={value} />
    {/each}
</div>

<style>
    .attr-list {
        display: flex;
        flex-direction: column;
        gap: 0.75rem;
    }
</style>