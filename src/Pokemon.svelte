<script lang="ts">
    $: roles = [
        {"name": "Support", "include": true},
        {"name": "Defender", "include": true},
        {"name": "Attacker", "include": true},
        {"name": "All-Rounder", "include": true},
        {"name": "Speedster", "include": true},
    ];

    export let pokes;
    export let showPokes;

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
        <div class="roles-buttons">
            {#each roles as { name, include }, i}
            <input type="checkbox" name={name} id={name} on:change={(e)=> {
            togglesPokesFromRow(e.target.name, !include);
            include = !include;
            }} checked={include}>
            <label class="role" for={name}>
                {name}
            </label>
            {/each}
        </div>
        <button on:click={togglePokesArea}>{showPokes ? "Hide" : "Show"} All Pokemon</button>
    </div>


    <hr />

    {#if showPokes }
    {#key pokes}
    <div id="pokemon-area">
        {#each pokes as poke(poke.id)}

        <input type="checkbox" name={poke.name} id={poke.name} bind:checked={poke.include}>
        <label class="pokemon" for={poke.name}>
            {poke.name}
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
        justify-content: space-between;
        color: white;
    }

    .roles-buttons {
        width: 90%;
        display: flex;
    }

    .role {
        width: 20%;
        display: flex;
        flex-direction: column;
        border: 1px solid darkgrey;
        font-size: 1.5rem;
        background: #45337b;
        cursor: pointer;
        padding-top: 5px;
    }

    .role:hover {
        background: #6a4ebf;
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
        color: white;
        background: #45337b;
        border: 1px solid #1a1137;
        font-size: 1.2rem;
    }

    .pokemon:hover {
        background: #6a4ebf;
        cursor: pointer;
    }

</style>
