<template>
    <div>
        <div><h3>Doors</h3></div>
        <div class="lmr-doors-top">
            <template v-for="door of doors">
                <div class="lmr-doors-row-first">
                    {{door.name}}
                </div>
                <div>
                    <lmr-pair-selector :entries="doors"/>
                </div>
            </template>
        </div>
    </div>
</template>

<script>
import LMRPairSelector from './LMRPairSelector.vue'

export default {
    name: 'lmr-door-tracker',
    components: {
        'lmr-pair-selector': LMRPairSelector
    },
    props: {
        doors: Array
    }
}
</script>

<style>
.lmr-doors-top {
    display: grid;
    grid-template-columns: auto auto;
    column-gap: 1.5em;
}

.lmr-doors-row-first {
    text-align: right
}
</style>
