<script>
import axios from 'axios';
import BreweryCard from './AppCard.vue';

export default {
    components: {
        BreweryCard,
    },
    data() {
        return {
            breweries: [],
        };
    },
    mounted() {
        axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=ireland&per_page=10")
            .then(response => {
                this.breweries = response.data;
            })
            .catch(error => {
                console.error('Errore nella chiamata API:', error);
            });
    },
};
</script>

<template>
    <section>
        <BreweryCard v-for="brewery in breweries" :key="brewery.id" :data="brewery" />
    </section>
</template>

<style scoped></style>
