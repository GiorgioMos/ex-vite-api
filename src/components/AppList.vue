<script>
import BreweryCard from './AppCard.vue';

export default {
    components: {
        BreweryCard,
    },
    props: {
        breweries: {
            type: Array,
        },
    },
};
</script>

<template>
    <section class="card-container">
        <BreweryCard v-for="brewery in breweries" :key="brewery.id" :data="brewery" />
    </section>
</template>

<style scoped>
.card-container {
    display: flex;
    flex-wrap: wrap;
}
</style>
