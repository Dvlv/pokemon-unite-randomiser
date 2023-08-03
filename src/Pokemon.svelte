<script lang="ts">
    $: roles = [
        {"name": "Support", "include": true},
        {"name": "Defender", "include": true},
        {"name": "Attacker", "include": true},
        {"name": "All-Rounder", "include": true},
        {"name": "Speedster", "include": true},
    ];

    export let pokes;
    let showPokes = false;

    function togglePokesArea() {
        showPokes = !showPokes;
    }

    function togglesPokesFromRow(rowName, rowInclude) {
        pokes.map(function (p) {
            if (p.type == rowName) {
                p.include = rowInclude;
            }
        })
        pokes = pokes;
    }

</script>
<div id="pokemon-main">
    <div id="roles-area">
        {#each roles as { name, include }, i}
        <label class="role">
            <input type="checkbox" name={name} on:change={(e)=> {
            togglesPokesFromRow(e.target.name, !include);
            include = !include;
            }} checked={include}>
            <br />
            {name}
        </label>
        {/each}
        <button on:click={togglePokesArea}>{showPokes ? "Hide" : "Show"} All Pokemon</button>
    </div>


    <hr />

    {#if showPokes }
    {#key pokes}
    <div id="pokemon-area">
        {#each pokes as poke(poke.id)}
        <label class="pokemon">
            <input type="checkbox" name={poke.name} bind:checked={poke.include}> {poke.name}
        </label>
        {/each}
    </div>

    <hr />
    {/key}
    {/if}
</div>

<style>
    #roles-area {
        display: flex;
        flex-direction: row;
        margin-bottom: 20px;
        align-items: center;
        justify-content: center;
    }

    .role {
        width: 20%;
        display: flex;
        flex-direction: column;

    }


    #pokemon-area {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        width: 100%;
        align-items: center;
        justify-content: center;
    }

    .pokemon {
        width: 10%;
        display: flex;
        flex-direction: column;
        padding: 15px 0;
    }

</style>
