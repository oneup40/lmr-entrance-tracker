<template>
    <div>
        <div><h3>Doors</h3></div>
        <div class="lmr-doors-top">
            <template v-for="door of doors">
                <div class="lmr-doors-row-first" :key="door + '-first'">
                    {{door}}
                </div>
                <div :key="door + '-second'">
                    <LMRPairSelector
                        :entries="doors"
                        :used="used"
                        @select="selected"
                        @deselect="deselected"
                    />
                </div>
            </template>
        </div>
    </div>
</template>

<script>
import LMRPairSelector from './LMRPairSelector.vue'

export default {
    name: 'LMRDoorTracker',
    components: {
        LMRPairSelector
    },
    props: {
        doors: Array
    },
    data() {
        let used = {};
        for (let door of this.$props.doors) {
            used[door] = false;
        }
        
        return {
            used: used
        }
    },
    methods: {
        selected: function(name) {
            this.$data.used[name] = true;
        },
        deselected: function(name) {
            this.$data.used[name] = false;
        }
    }
}
</script>

<style scoped>
.lmr-doors-top {
    display: grid;
    grid-template-columns: auto auto;
    column-gap: 1.5em;
}

.lmr-doors-row-first {
    text-align: right
}
</style>
