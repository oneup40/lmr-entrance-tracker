<template>
    <div>
        <div><h3>{{title}}</h3></div>
        <div class="lmr-pairs-top">
            <template v-for="(_, ndx) of pairs.first">
                <div class="lmr-pairs-row-first">
                    {{pairs.first[ndx]}}
                </div>
                <div>
                    <lmr-pair-selector :entries="pairs.second" />
                </div>
                <div class="lmr-pairs-spacer"/>
                <div class="lmr-pairs-row-second"
                    v-bind:class="{used: pairs.second[ndx].used}"
                >
                    {{pairs.second[ndx].name}}
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
    data: () => ({
    })
}
</script>

<style>
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
