<template>
    <div>
        <div><h3>{{title}}</h3></div>
        <div class="lmr-pairs-top">
            <template v-for="(_, ndx) of pairs.first">
                <div class="lmr-pairs-row-first" :key="pairs.first[ndx] + '-first'">
                    {{pairs.first[ndx]}}
                </div>
                <div :key="pairs.first[ndx] + '-selector'">
                    <lmr-pair-selector
                        :entries="pairs.second"
                        :used="used"
                        @select="selected"
                        @deselect="deselected"
                    />
                </div>
                <div class="lmr-pairs-spacer" :key="pairs.first[ndx] + '-spacer'"/>
                <div class="lmr-pairs-row-second"
                    :class="{used: used[pairs.second[ndx]]}"
                    :key="pairs.first[ndx] + '-second'"
                >
                    {{pairs.second[ndx]}}
                </div>
            </template>
        </div>
    </div>
</template>

<script>
import LMRPairSelector from './LMRPairSelector.vue'

export default {
    name: 'lmr-pair-tracker',
    components: {
        'lmr-pair-selector': LMRPairSelector
    },
    props: {
        title: String,
        pairs: Object
    },
    data() {
        let used = {};

        for (let name of this.$props.pairs.second) {
            used[name] = false;
        }

        return {
            used: used
        };
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
.lmr-pairs-top {
    display: grid;
    grid-template-columns: auto auto 1fr auto;
    column-gap: 1.5em;
}

.lmr-pairs-row-first {
    text-align: right;
    overflow: hidden;
}

.lmr-pairs-row-second {
    text-align: left;
}

.lmr-pairs-row-second.used {
    text-decoration: line-through;
    color: darkgray;
}

.lmr-pairs-spacer {
    flex-grow: 1;
}
</style>
