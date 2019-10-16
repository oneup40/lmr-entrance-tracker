<template>
    <select>
        <option>---</option>
        <option v-for="entry of entries" v-bind:key="entry">
            {{entry}}
        </option>
    </select>
</template>

<script>

export default {
    name: 'LMRPairSelector',
    props: {
        entries: Array
    }
}
</script>
