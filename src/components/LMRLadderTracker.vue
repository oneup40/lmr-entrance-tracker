<template>
    <div>
        <div><h3>Ladders</h3></div>
        <div class="ladder-top">
            <template v-for="(_, ndx) of groups[0]">
                <div class="ladder-up-row">
                    {{groups[0][ndx]}}
                </div>
                <div>
                    <LMRPairSelector :entries="groups[1]"/>
                </div>
                <div/>
                <div class="ladder-down-row">
                    {{groups[1][ndx]}}
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
        groups: Array
    },
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

.ladder-spacer {
    flex-grow: 1;
}
</style>
