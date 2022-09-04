<script lang="ts">
    import Data from "$lib/_data"
    import InsturmentCard from "$lib/components/insturmentCard.svelte";
</script>



<div id="container">

    {#each Data as {src, brand, model, id}}
        <InsturmentCard {src}  {id} header={brand} content={model}  />
    {/each}
</div>




<style lang="less">
    #container {
        display: grid;
        gap: 2rem;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        padding: 0  0 0 2rem ;
    }
</style>