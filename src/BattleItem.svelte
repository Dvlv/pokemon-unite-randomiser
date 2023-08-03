<script lang="ts">
    export let chooseBattleItem;
    export let battleItems;
</script>



<div id="battle-items-main">
    <label>
        <input name="battle" type="checkbox" bind:checked={chooseBattleItem}>
        Choose Battle Item
    </label>

    {#if chooseBattleItem}
    <hr />

    <div id="battleitem-area">
        {#each battleItems as battleItem(battleItem.id)}
        <label class="item">
            <input type="checkbox" name={battleItem.name} bind:checked={battleItem.include}> {battleItem.name}
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
    }

</style>
