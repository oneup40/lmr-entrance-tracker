<template>
    <div class="tracker-top">
        <LMRGateTracker/>
        <LMRLadderTracker :groups="[ladders.up, ladders.down]"/>
        <LMRDoorTracker/>
    </div>
</template>

<script>
import LMRGateTracker from './LMRGateTracker.vue'
import LMRLadderTracker from './LMRLadderTracker.vue'
import LMRDoorTracker from './LMRDoorTracker.vue'

export default {
    name: 'LMREntranceTracker',
    components: {
        LMRGateTracker,
        LMRLadderTracker,
        LMRDoorTracker
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
                "Guidance T",
                "Mausoleum T (Secret)",
            ]
        }
    })
}
</script>

<style>

.tracker-top {
    max-width: 800px;
}

</style>
