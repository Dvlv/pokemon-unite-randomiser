<script lang="ts">
    import Pokemon from './Pokemon.svelte';
    import BattleItem from './BattleItem.svelte';
    import HeldItems from './HeldItems.svelte';

    let pokes = [
        {"name": "Absol", "type": "Speedster", "include": true, },
        {"name": "Aegislash", "type": "All-Rounder", "include": true, },
        {"name": "Azumarill", "type": "All-Rounder", "include": true, },
        {"name": "Blastoise", "type": "Defender", "include": true, },
        {"name": "Blissey", "type": "Support", "include": true, },
        {"name": "Buzzwole", "type": "All-Rounder", "include": true, },
        {"name": "Chandelure", "type": "Attacker", "include": true, },
        {"name": "Charizard", "type": "All-Rounder", "include": true, },
        {"name": "Cinderace", "type": "Attacker", "include": true, },
        {"name": "Clefable", "type": "Support", "include": true, },
        {"name": "Comfey", "type": "Support", "include": true, },
        {"name": "Cramorant", "type": "Attacker", "include": true, },
        {"name": "Crustle", "type": "Defender", "include": true, },
        {"name": "Decidueye", "type": "Attacker", "include": true, },
        {"name": "Delphox", "type": "Attacker", "include": true, },
        {"name": "Dodrio", "type": "Speedster", "include": true, },
        {"name": "Dragapult", "type": "Attacker", "include": true, },
        {"name": "Dragonite", "type": "All-Rounder", "include": true, },
        {"name": "Duraludon", "type": "Attacker", "include": true, },
        {"name": "Eldegoss", "type": "Support", "include": true, },
        {"name": "Espeon", "type": "Attacker", "include": true, },
        {"name": "Garchomp", "type": "All-Rounder", "include": true, },
        {"name": "Gardevoir", "type": "Attacker", "include": true, },
        {"name": "Gengar", "type": "Speedster", "include": true, },
        {"name": "Glaceon", "type": "Attacker", "include": true, },
        {"name": "Goodra", "type": "Defender", "include": true, },
        {"name": "Greedent", "type": "Defender", "include": true, },
        {"name": "Greninja", "type": "Attacker", "include": true, },
        {"name": "Hoopa", "type": "Support", "include": true, },
        {"name": "Inteleon", "type": "Attacker", "include": true, },
        {"name": "Lapras", "type": "Defender", "include": true, },
        {"name": "Leafeon", "type": "Speedster", "include": true, },
        {"name": "Lucario", "type": "All-Rounder", "include": true, },
        {"name": "Machamp", "type": "All-Rounder", "include": true, },
        {"name": "Mamoswine", "type": "Defender", "include": true, },
        {"name": "Mew", "type": "Attacker", "include": true, },
        {"name": "Mewtwo", "type": "All-Rounder", "include": true, },
        {"name": "Mr Mime", "type": "Support", "include": true, },
        {"name": "Ninetales", "type": "Attacker", "include": true, },
        {"name": "Pikachu", "type": "Attacker", "include": true, },
        {"name": "Sableye", "type": "Support", "include": true, },
        {"name": "Scizor", "type": "All-Rounder", "include": true, },
        {"name": "Scyther", "type": "All-Rounder", "include": true, },
        {"name": "Slowbro", "type": "Defender", "include": true, },
        {"name": "Snorlax", "type": "Defender", "include": true, },
        {"name": "Sylveon", "type": "Attacker", "include": true, },
        {"name": "Talonflame", "type": "Speedster", "include": true, },
        {"name": "Trevenant", "type": "Defender", "include": true, },
        {"name": "Tsareena", "type": "All-Rounder", "include": true, },
        {"name": "Tyranitar", "type": "All-Rounder", "include": true, },
        {"name": "Umbreon", "type": "Defender", "include": true, },
        {"name": "Urshifu", "type": "Attacker", "include": true, },
        {"name": "Venusaur", "type": "Attacker", "include": true, },
        {"name": "Wigglytuff", "type": "Support", "include": true, },
        {"name": "Zacian", "type": "All-Rounder", "include": true, },
        {"name": "Zeraora", "type": "Speedster", "include": true, },
        {"name": "Zoroark", "type": "Speedster", "include": true, },
    ]

    pokes.forEach(function (p, i) {
        p.id = i;
    })

    let battleItems = [
        {"name": "Shedinja Doll", "include": true, },
        {"name": "Eject Button", include: true, },
        {"name": "X-Attack", include: true, },
        {"name": "X-Speed", include: true, },
        {"name": "Goal Getter", include: true, },
        {"name": "Slow Smoke", include: true, },
        {"name": "Fluffy Tail", include: true, },
        {"name": "Full Heal", include: true, },
        {"name": "Potion", include: true, },
    ]

    battleItems.forEach(function (h, i) {
        h.id = i;
    })

    let heldItems = [
        {"name": "Aeos Cookie", "include": true, },
        {"name": "Assault Vest", include: true, },
        {"name": "Attack Weight", include: true, },
        {"name": "Buddy Barrier", include: true, },
        {"name": "Choice Specs", include: true, },
        {"name": "Drain Crown", include: true, },
        {"name": "Energy Amplifier", include: true, },
        {"name": "Exp. Share", include: true, },
        {"name": "Float Stone", include: true, },
        {"name": "Focus Band", include: true, },
        {"name": "Leftovers", include: true, },
        {"name": "Muscle Band", include: true, },
        {"name": "Rapid-Fire Scarf", include: true, },
        {"name": "Razor Claw", include: true, },
        {"name": "Rescue Hood", include: true, },
        {"name": "Rocky Helmet", include: true, },
        {"name": "Scope Lens", include: true, },
        {"name": "Score Shield", include: true, },
        {"name": "Shell Bell", include: true, },
        {"name": "Slick Spoon", include: true, },
        {"name": "Sp. Atk Specs", include: true, },
        {"name": "Weakness Policy", include: true, },
        {"name": "Wise Glasses", include: true, },
    ]

    heldItems.forEach(function (h, i) {
        h.id = i;
    })

    let showPokes = false;

    let chosenMon;
    let chosenHelds = [];
    let chosenBattle;

    $: chooseBattleItem = false;
    $: chooseHeldItem = false;

    function randGen(max) {
        return Math.floor(Math.random() * max)
    }

    function getRandomMon() {
        showPokes = false;
        chosenHelds = [];
        chosenBattle = "";

        let pokesAvail = pokes.filter(function (p) {
            return p.include;
        })

        if (pokesAvail.length == 0) {
            chosenMon = {name: "No Pokemon To Choose From :("}
        } else {
            for (let i = 0; i < 10; i++) {
                setTimeout(function () {
                    chosenMon = pokesAvail[randGen(pokesAvail.length)]
                    chosenMon.final = false;
                }, 50 * i);
            }

            setTimeout(function () {
                chosenMon = pokesAvail[randGen(pokesAvail.length)];
                chosenMon.final = true;
                if (chooseHeldItem) {
                    getRandomHeldItem();
                }
                if (chooseBattleItem) {
                    getRandomBattleItem();
                }
            }, 500);
        }
    }

    function getRandomHeldItem() {
        let heldsAvail = heldItems.filter(function (h) {
            return h.include;
        });

        if (heldsAvail.length > 0) {
            let randOne = randGen(heldsAvail.length);
            let randTwo = randGen(heldsAvail.length);
            while (randTwo == randOne) {
                randTwo = randGen(heldsAvail.length);
            }

            let randThree = randGen(heldsAvail.length);
            while (randThree == randOne || randThree == randTwo) {
                randThree = randGen(heldsAvail.length);
            }

            chosenHelds[0] = heldsAvail[randOne];
            chosenHelds[1] = heldsAvail[randTwo];
            chosenHelds[2] = heldsAvail[randThree];
        }
    }

    function getRandomBattleItem() {
        let battlesAvail = battleItems.filter(function (h) {
            return h.include;
        });

        if (battlesAvail.length > 0) {
            chosenBattle = battlesAvail[randGen(battlesAvail.length)];
        }
    }

</script>

<main>
    <h1>Unite Randomizer</h1>

    {#if chosenMon}
    <div id="chosen-mon" style="color: {chosenMon.final ? 'gold' :'grey'}">
    <img src="{chosenMon.name}.png">
    {chosenMon.name}
    </div>
    {/if}

    {#if chosenBattle}
    <div id="chosen-battle">{chosenBattle.name}</div>
    {/if}

    {#if chosenHelds.length}
    <div id="chosen-held-wrapper">
    {#each chosenHelds as chosenHeld}
    <div id="chosen-held">{chosenHeld.name}</div>
    {/each}
    </div>
    {/if}

    <button id="main-btn" on:click={getRandomMon}>Randomize!</button>

    <div class="card">
        <Pokemon pokes={pokes} bind:showPokes />
        <BattleItem bind:chooseBattleItem battleItems={battleItems} />
        <HeldItems bind:chooseHeldItem heldItems={heldItems} />
    </div>




</main>

<style>
    #chosen-mon {
        font-size: 3.5rem;
        font-weight: bold;
        background: #6a4ebf;
        width: 30%;
        border-radius: 20px;
        margin: 0 auto;
        margin-bottom: 20px;
        display: flex;
        flex-direction: column;
    }

    #chosen-mon img {
        width: 128px;
        height: 128px;
        margin: 10px auto 0 auto;
    }


    #chosen-battle {
        font-size: 1.6rem;
        margin: 20px;
        margin-bottom: 30px;
        background: #6a4ebf;
        width: 20%;
        border-radius: 20px;
        margin: 0 auto;
        margin-bottom: 20px;
    }

    #chosen-held-wrapper {
        background: #6a4ebf;
        width: 15%;
        border-radius: 20px;
        margin: 0 auto;
        margin-bottom: 20px;
        padding: 5px 0;
    }

    #chosen-held {
        font-size: 1.2rem;
        margin: 10px 0;
    }

    #main-btn {
    font-size: 1.8rem;
    font-weight: bold;
    }

</style>
