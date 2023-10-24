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

    <div class="container-fluid">
      <div class="row">
        <div class="col-4">
          <h1 class="contacts">Contattaci</h1>
        </div>

        <div class="col-8">
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
                rows="10"
                v-model="formContact.message"
              ></textarea>
            </div>
            <button type="submit" class="btn btn-primary rounded-pill customBtn">Invia</button>
          </form>
        </div>
      </div>
    </div>
    
    
    <div v-if="dataSendSuccess">{{ dataSendSuccess }}</div>
  </div>
</template>

<style scoped>
input[type=text]{
  font-size: 40px;
  background-color: transparent;
  border: 0;
  border-radius: 0;
  border-bottom: 1px solid white;
}

input[type=email]{
  font-size: 40px;
  background-color: transparent;
  border: 0;
  border-radius: 0;
  border-bottom: 1px solid white;
}

textarea{
  background-color: transparent;
  border: 0;
  border-radius: 0;
  border-bottom: 1px solid white;
}

.form-label{
  text-transform: uppercase;
  font-family: 'Karla', serif;
  font-weight: 500;
  color: #D1B875;
  font-size: 14px;
}

.col-4{
  padding: 0;
  margin: 0;
}

.customBtn{
  background-color: #D1B875;
  padding: 16px 32px;
  color: black;
  text-transform: uppercase;
}

.contacts{
  font-family: 'Playfair Display', serif;
  font-weight: 400;
  color: white;
  font-size: 56px;
  margin-top: -5px;
}

.container-fluid {
  margin-top: 80px;
}
</style>
