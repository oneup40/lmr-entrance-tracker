<template>
    <select class="pair-selector" @change="changed" v-model="selected">
        <option v-bind:value="'---'">---</option>
        <option v-for="entry of unusedEntries" :key="entry" v-bind:value="entry">
            {{entry}}
        </option>
    </select>
</template>

<script>

export default {
    name: 'lmr-pair-selector',
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

<style>
.pair-selector {
    width: 100%
}
</style>
