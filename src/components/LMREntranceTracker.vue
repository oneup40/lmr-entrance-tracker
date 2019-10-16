<template>
    <div class="tracker-top">
        <LMRGateTracker/>
        <LMRLadderTracker/>
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
    })
}
</script>

<style>

.tracker-top {
    max-width: 800px;
}

</style>
