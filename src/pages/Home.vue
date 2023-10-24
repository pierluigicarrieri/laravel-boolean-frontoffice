<script>
  import axios from 'axios';
  import Card from '../components/Card.vue';

  export default {
    components: {
      Card
    },

    data() {
      return {
        cocktails: [],
        searchData: {
        "name" : "",
        "alcoholic" : "",
        }
      }
    },

    methods: {
      fetchData() {
        axios.get("http://127.0.0.1:8000/api/cocktails", {
          params: this.searchData,})
        .then((response) => {
          this.cocktails = response.data;
          // console.log(response.data);
          console.log(this.searchData);
          console.log(response.data);
        })
      },

      searchCocktail() {
        this.fetchData();
      },

      resetSearch() {
        this.searchData.name = "";
        this.searchData.alcoholic = "";
        this.fetchData();
      },

      getImageURL(project) {
        return `http://127.0.0.1:8000/storage/${project.imageURL}`
      }
    },

    mounted() {
      this.fetchData();
    }
  }
</script>

<template>
    <h1 class="text-center pt-3">Lista dei progetti</h1>

    <div class="container mt-4">

      <form class="w-25 mb-5" @submit.prevent="searchCocktail" @reset="resetSearch">
        <input type="text" placeholder="Scrivi cocktail da cercare" class="form-control" v-model="searchData.name">
        <select class="form-select" v-model="searchData.alcoholic" aria-label="Alcoholic Content">
          <option value="" selected>Tutti</option>
          <option value="1">Alcolici</option>
          <option value="0">Analcolici</option>
        </select>
        <div class="mt-3 d-flex gap-2">
          <button class="btn btn-primary" type="submit">Cerca</button>
          <button class="btn btn-danger" type="reset">Svuota</button>
        </div>
      </form>

        <div class="row">
        <div class="col-4" v-for="cocktail in this.cocktails" :key="cocktail.id">
            <Card :cocktail="cocktail"></Card>
        </div>
        </div>
    </div>   
</template>

<style>

</style>