<script lang="ts">
    export let chooseHeldItem;
    export let heldItems;
</script>



<div id="held-items-main">
    <label>
        <input name="held" type="checkbox" bind:checked={chooseHeldItem}>
        Choose Held Items
    </label>

    {#if chooseHeldItem}
    <hr />

    <div id="helditem-area">
        {#each heldItems as heldItem(heldItem.id)}
        <label class="item">
            <input type="checkbox" name={heldItem.name} bind:checked={heldItem.include}> {heldItem.name}
        </label>
        {/each}
    </div>
    {/if}
</div>

<style>
    #helditem-area {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        width: 100%;
        align-items: center;
        justify-content: center;
    }

    .item {
        width: 10%;
        display: flex;
        flex-direction: column;
        padding: 15px 0;
    }

</style>
