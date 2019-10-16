<template>
    <div>
        <div><h3>Ladders</h3></div>
        <div class="ladder-top">
            <template v-for="(_, ndx) of ladders.up">
                <div class="ladder-up-row" v-bind:key="ladders.up[ndx]">
                    {{ladders.up[ndx]}}
                </div>
                <div v-bind:key="ndx + '-selector'">
                    <LMRPairSelector :entries="ladders.down" />
                </div>
                <div v-bind:key="ndx + '-spacer'" />
                <div class="ladder-down-row"
                    v-bind:class="{used: ladders.down[ndx].used}"
                    v-bind:key="ladders.down[ndx].name"
                >
                    {{ladders.down[ndx].name}}
                </div>
            </template>
        </div>
    </div>
</template>

<script>
import LMRPairSelector from './LMRPairSelector.vue'

export default {
    name: 'LMRLadderTracker',
    components: {
        LMRPairSelector
    },
    props: {
    },
    data: () => ({
        ladders: {
            up: [
                "Guidance (Shuriken)",
                "Mausoleum (Top)",
                "TotS (Top)",
                "Inferno Lower (Map)",
                "Inferno Upper (Spikes)",
                "Extinction (Main)",
                "Extinction (Palenque)",
                "Extinction (Magatama)",
                "TL Left (Closed)",
                "TL Middle (Poison)",
                "TL Right (Crystal Skull)",
                "Endless (Philosopher)",
                "Shrine Entrance (Top)",
                "Graveyard Left (Hot Spring)",
                "Gravevard Right (Lamp Refill)",
                "Moonlight Left (Coin Chest)",
                "Moonlight Right (Falling Block Trap)",
                "Goddess (Lamp Refill)",
                "Birth (Backside Door)",
                "Mausoleum T (Top)",
            ],
            down: [
                { name: "Surface Left", used: false },
                { name: "Surface Right", used: false },
                { name: "Guidance Left (Guild Shop)", used: false },
                { name: "Guidance Right (Ankh Jewel)", used: false },
                { name: "Mausoleum (Ankh Switch)", used: false },
                { name: "Spring", used: false },
                { name: "TL Left (Fairy Point)", used: false },
                { name: "TL Right (Broken Elevator)", used: false },
                { name: "Endless (Bottom)", used: false },
                { name: "Shrine Main (Elevator)", used: false },
                { name: "Shrine A (Unblocked Annex)", used: false },
                { name: "Shrine B (Blocked Annex)", used: false },
                { name: "Illusion Left (One Way Doors)", used: false },
                { name: "Illusion Right (Eden)", used: false },
                { name: "Graveyard (Kamitachi)", used: false },
                { name: "Goddess (Shield Trap)", used: false },
                { name: "Birth (Grail Tablet)", used: false },
                { name: "DC (Entrance)", used: false },
                { name: "Guidance T", used: false },
                { name: "Mausoleum T (Secret)", used: false },
            ]
        }
    })
}
</script>

<style>
.ladder-top {
    display: grid;
    grid-template-columns: auto auto 1fr auto;
    column-gap: 1.5em;
}

.ladder-up-row {
    text-align: right;
    overflow: hidden;
}

.ladder-down-row {
    text-align: left;
}

.ladder-down-row.used {
    text-decoration: line-through;
    color: darkgray;
}

.ladder-spacer {
    flex-grow: 1;
}
</style>
