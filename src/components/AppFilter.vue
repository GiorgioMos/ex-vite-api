<script>
export default {
    data() {
        return {
            searchTerm: '',
        };
    },
    methods: {
        searchBreweries() {
            this.$emit('search', this.searchTerm);
        },
    },
};
</script>
<template>
    <div>
        <input v-model="searchTerm" placeholder="Search by name" />
        <button @click="searchBreweries">Search</button>
    </div>
</template>

<style scoped></style>