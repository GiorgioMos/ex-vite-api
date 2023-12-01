<script>
export default {
    props: {
        data: {
            type: Object,
        },
    },
};
</script>

<template>
    <div class="card">
        <h2>{{ data.name }}</h2>
    </div>
</template>

<style scoped>
.card {
    margin: 2rem;
    background-color: rgb(44, 117, 185);
    display: flex;
    color: black;
    justify-content: center;
    border-radius: 1rem;
    border: solid;
    padding: 1rem;
    width: 300px;
}
</style>