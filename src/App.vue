<script>
import axios from 'axios';
import AppList from './components/AppList.vue';

export default {
    components: {
        AppList,
    },
    mounted() {
        axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=scotland&per_page=10").then(risultato => {
            console.log(risultato)
        })
    }
};

</script>

<template>
    <div>
        <AppList />
    </div>
</template>

<style scoped></style>
