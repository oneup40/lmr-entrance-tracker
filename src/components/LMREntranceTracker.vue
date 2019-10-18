<template>
    <div class="lmr-tracker-top">
        <LMRPairTracker
            title="Gates"
            :pairs="gatePairs"
        />
        <LMRPairTracker
            title="Ladders"
            :pairs="ladderPairs"
        />
        <LMRDoorTracker :doors="doors"/>
    </div>
</template>

<script>
import LMRDoorTracker from './LMRDoorTracker.vue'
import LMRPairTracker from './LMRPairTracker.vue'

export default {
    name: 'LMREntranceTracker',
    components: {
        LMRPairTracker,
        LMRDoorTracker,
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
                "Goddess (Time Exit)",
            ],
            down: [
                "Surface Left",
                "Surface Right",
                "Guidance Left (Guild Shop)",
                "Guidance Right (Ankh Jewel)",
                "Mausoleum (Ankh Switch)",
                "Spring",
                "TL Left (Fairy Point)",
                "TL Right (Broken Elevator)",
                "Endless (Bottom)",
                "Shrine Main (Elevator)",
                "Shrine A (Unblocked Annex)",
                "Shrine B (Blocked Annex)",
                "Illusion Left (One Way Doors)",
                "Illusion Right (Eden)",
                "Graveyard (Kamitachi)",
                "Goddess (Shield Trap)",
                "Birth (Grail Tablet)",
                "DC (Entrance)",
                "Guidance [Time]",
                "Mausoleum [Time] (Secret)",
                "Inferno (LAVA)",
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
                "Birth (Skanda)",
                "Surface [Time] (Ruins Entrance)",
            ],
            right: [
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
                "Birth (Woman Statue)",
                "Guidance [Time]",
            ]
        },

        doors: [
            "Surface (Waterfall)",
            "Guidance (yagostr.exe)",
            "Mausoleum",
            "TotS",
            "Inferno Lower (Ankh)",
            "Inferno Upper (Spikes)",
            "Extinction Lower (Grail)",
            "Extinction Upper (Magatama)",
            "Endless (Exit Only)",
            "Illusion",
            "Graveyard",
            "Moonlight",
            "Goddess",
            "Ruin Lower (Earth Spear)",
            "Ruin Upper (Nuwa)",
            "Birth",
            "DC",
            "Time",
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

<style scoped>
.lmr-tracker-top {
    max-width: 800px;
}
</style>
