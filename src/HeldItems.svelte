<script lang="ts">
    export let chooseHeldItem;
    export let heldItems;
</script>



<div id="held-items-main">
    <input name="held" type="checkbox" id="held" bind:checked={chooseHeldItem}>
    <label id="held-label" for="held">
        Random Held Items
    </label>

    {#if chooseHeldItem}
    <hr />

    <div id="helditem-area">
        {#each heldItems as heldItem(heldItem.id)}
        <input type="checkbox" name={heldItem.name} id={heldItem.name} bind:checked={heldItem.include}>
        <label class="item" for={heldItem.name}>
            {heldItem.name}
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
        color: white;
        background: #45337b;
        border: 1px solid #1a1137;
        font-size: 1.2rem;
    }

    .item:hover {
        background: #6a4ebf;
        cursor: pointer;
    }

    #held-label:before {
        display: inline-block;
        margin: 0;
        width: 25px;
        height: 25px;
        margin-right: 15px;
    }

    #held-label {
        font-size: 1.3rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }

</style>
