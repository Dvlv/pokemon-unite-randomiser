<script lang="ts">
    export let chooseBattleItem;
    export let battleItems;
</script>



<div id="battle-items-main">
    <input name="battle" id="battle" type="checkbox" bind:checked={chooseBattleItem}>
    <label for="battle" id="battle-label">
        Random Battle Item
    </label>

    {#if chooseBattleItem}
    <hr />

    <div id="battleitem-area">
        {#each battleItems as battleItem(battleItem.id)}
        <input type="checkbox" name={battleItem.name} id={battleItem.name} bind:checked={battleItem.include}>
        <label class="item" for={battleItem.name}>
            {battleItem.name}
        </label>
        {/each}
    </div>
    {/if}
</div>

<style>
    #battleitem-area {
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

    label#battle-label:before {
        display: inline-block;
        margin: 0;
        width: 25px;
        height: 25px;
        margin-right: 15px;
    }

    label#battle-label {
        font-size: 1.3rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }

</style>
