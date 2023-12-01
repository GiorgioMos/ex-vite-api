<script>
import axios from 'axios';
import AppList from './components/AppList.vue';
import AppFilter from './components/AppFilter.vue';

export default {
    components: {
        AppList,
        AppFilter,
    },
    data() {
        return {
            breweries: [],
            filteredBreweries: [],
        };
    },
    mounted() {
        this.fetchBreweries();
    },
    methods: {
        fetchBreweries() {
            axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=austria&per_page=10")
                .then(response => {
                    this.breweries = response.data;
                    this.filteredBreweries = this.breweries;
                });
        },
        handleSearch(input) {
            if (input.trim() === '') {
                this.filteredBreweries = this.breweries;
            } else {
                this.filteredBreweries = this.breweries.filter(brewery =>
                    brewery.name.toLowerCase().includes(input.toLowerCase())
                );
            }
        },
    },
};
</script>


<template>
    <div>
        <AppFilter @search="handleSearch" />
        <AppList :breweries="filteredBreweries" />
    </div>
</template>

<style scoped></style>
