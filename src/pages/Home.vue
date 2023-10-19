<script>
  import axios from 'axios';
  import Card from '../components/Card.vue';

  export default {
    components: {
      Card
    },

    data() {
      return {
        cocktails: []
      }
    },

    methods: {
      fetchData() {
        axios.get("http://127.0.0.1:8000/api/cocktails")
        .then((response) => {
          this.cocktails = response.data;
          //console.log(response.data);
        })
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
        <div class="row">
        <div class="col-4" v-for="cocktail in this.cocktails" :key="cocktail.id">
            <Card :cocktail="cocktail"></Card>
        </div>
        </div>
    </div>   
</template>

<style>

</style>