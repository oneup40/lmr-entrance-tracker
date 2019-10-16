<template>
    <div class="tracker-top">
        <LMRGateTracker/>
        <LMRPairTracker title="Ladders" :pairs="ladderPairs"/>
        <LMRDoorTracker/>
    </div>
</template>

<script>
import LMRGateTracker from './LMRGateTracker.vue'
import LMRDoorTracker from './LMRDoorTracker.vue'
import LMRPairTracker from './LMRPairTracker.vue'

export default {
    name: 'LMREntranceTracker',
    components: {
        LMRGateTracker,
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
    }),

    computed: {
        ladderPairs: function() {
            return {
                first: this.$data.ladders.up,
                second: this.$data.ladders.down
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
