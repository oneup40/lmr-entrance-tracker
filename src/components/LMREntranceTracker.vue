<template>
    <div class="tracker-top">
        <LMRPairTracker title="Gates" :pairs="gatePairs"/>
        <LMRPairTracker title="Ladders" :pairs="ladderPairs"/>
        <LMRDoorTracker/>
    </div>
</template>

<script>
import LMRDoorTracker from './LMRDoorTracker.vue'
import LMRPairTracker from './LMRPairTracker.vue'

export default {
    name: 'LMREntranceTracker',
    components: {
        LMRDoorTracker,
        LMRPairTracker
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
                "Guidance (Entrance)",
                "Mausoleum (Left of Ankh)",
                "TotS (Buer)",
                "Extinction (Upper)",
                "Extinction (Lower)",
                "Graveyard (mirai.exe)",
                "Moonlight (Backside Door)",
                "Goddess (Bottom)",
                "Goddess (Spaulder)",
                "Ruin (Map)",
                "Birth (Skanda)",
                "Guidance [Time]"
            ],
            right: [
                { name: "Surface (Ruins Entrance)", used: false },
                { name: "TotS (Flooded Upper)", used: false },
                { name: "TotS (Flooded Lower)", used: false },
                { name: "Inferno (Lava Floats)", used: false },
                { name: "Endless (Top)", used: false },
                { name: "Illusion (Dancing Child)", used: false },
                { name: "Illusion (Chi You)", used: false },
                { name: "Graveyard (Grail)", used: false },
                { name: "Ruin (Medicine)", used: false },
                { name: "Ruin (Sacred Orb)", used: false },
                { name: "Birth (Woman Statue)", used: false },
                { name: "Surface [Time] (Ruins Entrance)", used: false }
            ]
        }
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
