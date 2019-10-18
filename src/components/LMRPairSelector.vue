<template>
    <select class="lmr-pair-selector" @change="changed" v-model="selected">
        <option :value="'---'">---</option>
        <option v-for="entry of unusedEntries" :key="entry" :value="entry">
            {{entry}}
        </option>
    </select>
</template>

<script>

export default {
    name: 'LMRPairSelector',
    data: () => ({
        lastSelected: '---',
        selected: '---',
    }),
    props: {
        entries: Array,
        used: Object
    },
    computed: {
        unusedEntries: function() {
            return this.$props.entries.filter(entry => !this.$props.used[entry] || entry == this.$data.selected)
        }
    },
    methods: {
        changed: function() { 
            if (this.$data.selected != '---') {
                this.$emit('select', this.$data.selected);
            }

            if (this.$data.lastSelected != '---') {
                this.$emit('deselect', this.$data.lastSelected);
            }

            this.$data.lastSelected = this.$data.selected;
        }
    }
}
</script>

<style scoped>
.lmr-pair-selector {
    width: 100%
}
</style>
