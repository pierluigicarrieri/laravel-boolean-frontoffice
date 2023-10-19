<script>
    export default {
        props: {
            cocktail: Array,
        }
    }
</script>

<template>

    <div class="card h-100">
        <img :src="cocktail.imageURL" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">Nome Progetto: {{cocktail.name}}</h5>
        </div>
    </div>
</template>

<style>
.card-img-top {
    height: 275px;
    object-fit: cover;
}
</style>