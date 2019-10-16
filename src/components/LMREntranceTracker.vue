<template>
    <div class="tracker-top">
        <lmr-pair-tracker title="Gates" :pairs="gatePairs"/>
        <lmr-pair-tracker title="Ladders" :pairs="ladderPairs"/>
        <lmr-door-tracker :doors="doors"/>
    </div>
</template>

<script>
import LMRDoorTracker from './LMRDoorTracker.vue'
import LMRPairTracker from './LMRPairTracker.vue'

export default {
    name: 'lmr-entrance-tracker',
    components: {
        'lmr-pair-tracker': LMRPairTracker,
        'lmr-door-tracker': LMRDoorTracker,
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
                "Mausoleum [Time] (Top)",
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
                { name: "Guidance [Time]", used: false },
                { name: "Mausoleum [Time] (Secret)", used: false },
            ]
        },

        gates: {
            left: [
                "Surface (Ruins Entrance)",
                "TotS (Flooded Upper)",
                "TotS (Flooded Lower)",
                "Inferno (Lava Floats)",
                "Endless (Top)",
                "Illusion (Dancing Child)",
                "Illusion (Chi You)",
                "Graveyard (Grail)",
                "Ruin (Medicine)",
                "Ruin (Sacred Orb)",
                "Birth (Woman Statue)",
                "Surface [Time] (Ruins Entrance)",
            ],
            right: [
                { name: "Guidance (Entrance)", used: false },
                { name: "Mausoleum (Left of Ankh)", used: false },
                { name: "TotS (Buer)", used: false },
                { name: "Extinction (Upper)", used: false },
                { name: "Extinction (Lower)", used: false },
                { name: "Graveyard (mirai.exe)", used: false },
                { name: "Moonlight (Backside Door)", used: false },
                { name: "Goddess (Bottom)", used: false },
                { name: "Goddess (Spaulder)", used: false },
                { name: "Ruin (Map)", used: false },
                { name: "Birth (Skanda)", used: false },
                { name: "Guidance [Time]", used: false },
            ]
        },

        doors: [
            {name: "Surface (Waterfall)", used: false},
            {name: "Guidance (yagostr.exe)", used: false},
            {name: "Mausoleum", used: false},
            {name: "TotS", used: false},
            {name: "Inferno Lower (Ankh)", used: false},
            {name: "Inferno Upper (Spikes)", used: false},
            {name: "Extinction Lower (Grail)", used: false},
            {name: "Extinction Upper (Magatama)", used: false},
            {name: "Endless (Exit Only)", used: false},
            {name: "Illusion", used: false},
            {name: "Graveyard", used: false},
            {name: "Moonlight", used: false},
            {name: "Goddess", used: false},
            {name: "Ruin Lower (Earth Spear)", used: false},
            {name: "Ruin Upper (Nuwa)", used: false},
            {name: "Birth", used: false},
            {name: "DC", used: false},
            {name: "Time", used: false}
        ]
    }),

    computed: {
        ladderPairs: function() {
            return {
                first: this.$data.ladders.up,
                second: this.$data.ladders.down
            }
        },

        gatePairs: function() {
            return {
                first: this.$data.gates.left,
                second: this.$data.gates.right
            }
        }
    }
}
</script>

<style>

.tracker-top {
    max-width: 800px;
}

</style>
