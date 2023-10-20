<script>
import axios from "axios";

export default {
  data() {
    return {
      formContact: {
        name: "",
        email: "",
        message: "",
      },
      dataSendSuccess: null,
    };
  },
  methods: {
    onClickForm() {
      axios
        .post("http://127.0.0.1:8000/api/contacts", this.formContact)
        .then((response) => {
          this.dataSendSuccess = response.data.message;
          console.log(response.data.dataContact);
        });
    },
  },
};
</script>

<template>
  <div class="container">
    <h1 class="text-center">Cocktail Bar Contatti</h1>
    <form @submit.prevent="onClickForm">
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Nome</label>
        <input
          type="text"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          v-model="formContact.name"
        />
      </div>
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Email</label>
        <input
          type="email"
          class="form-control"
          id="exampleInputEmail1"
          aria-describedby="emailHelp"
          v-model="formContact.email"
        />
      </div>
      <div class="mb-3">
        <label for="exampleInputText" class="form-label">Messaggio</label>
        <textarea
          type="text"
          class="form-control"
          id="exampleInputText"
          v-model="formContact.message"
        ></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Invia Dati</button>
    </form>
    <div v-if="dataSendSuccess">{{ dataSendSuccess }}</div>
  </div>
</template>

<style></style>
