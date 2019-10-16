<template>
    <select class="pair-selector" @change="changed" v-model="selected">
        <option v-bind:value="{name:'---'}">---</option>
        <option v-for="entry of unusedEntries" :key="entry.name" v-bind:value="entry">
            {{entry.name}}
        </option>
    </select>
</template>

<script>

export default {
    name: 'lmr-pair-selector',
    data: () => ({
        lastSelected: {name:'---'},
        selected: {name:'---'},
    }),
    props: {
        entries: Array
    },
    computed: {
        unusedEntries: function() {
            return this.$props.entries.filter(entry => !entry.used || entry.name == this.$data.selected.name)
        }
    },
    methods: {
        changed: function() { 
            console.log(this.$data.lastSelected.name, '-->', this.$data.selected.name);
            if (this.$data.selected.name != '---') {
                this.$data.selected.used = true;
            }
            this.$data.lastSelected.used = false;
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
