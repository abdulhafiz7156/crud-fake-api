<template>
  <div class="create__user__div">
    <div class="container">
      <div class="create__user__div__title">
        <h1>Сreate user</h1>
      </div>
      <div class="create__inputs">
        <div>
          <label for="name">Name</label>
          <input type="text" id="name" v-model="this.newUser.name">
        </div>
        <div>
          <label for="username">Username</label>
          <input type="text" id="username" v-model="this.newUser.username">
        </div>
        <div>
          <label for="email">Email</label>
          <input type="text" id="email" v-model="this.newUser.email" required>
        </div>
        <div>
          <label for="phone">Phone</label>
          <input type="text" id="phone" v-model="this.newUser.phone">
        </div>
        <div>
          <label for="website">Website</label>
          <input type="text" id="website" v-model="this.newUser.website">
        </div>
        <div>
          <label for="company">Company</label>
          <input type="text" id="company" v-model="this.newUser.company">
        </div>
        <div>
          <label for="city">City</label>
          <input type="text" id="city" v-model="this.newUser.address.city">
        </div>
        <div>
          <label for="street">Street</label>
          <input type="text" id="street" v-model="this.newUser.address.street">
        </div>
        <div class="special__inputs__div">
          <div>
            <label for="suite">Suite</label>
            <input type="text" id="suite" v-model="this.newUser.address.suite">
          </div>
          <div>
            <label for="zipcode">Zipcode</label>
            <input type="text" id="zipcode" v-model="this.newUser.address.zipcode">
          </div>
        </div>
      </div>
      <div class="create__user__div__btn">
        <button @click="createUser()" class="base__btn ">Create user</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import axios from "axios";
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CreateUser',
  data(){
    return {
      newUser: {
        name: "",
        username: "",
        email: "",
        address: {
          street: "",
          suite: "",
          city: "",
          zipcode: "",
        },
        phone: '',
        website: '',
        company: ''
      }
    }
  },
  methods: {
    createUser() {
      axios.post('https://jsonplaceholder.typicode.com/users/', {
        name: this.newUser.name,
        username: this.newUser.username,
        email: this.newUser.email,
        address: {
          street: this.newUser.address.street,
          suite: this.newUser.address.suite,
          city: this.newUser.address.city,
          zipcode: this.newUser.address.zipcode,
        },
        phone: this.newUser.phone,
        website: this.newUser.website,
        company: this.newUser.company
      })
      .then(response => {
        console.log(response);
        this.$router.push('/')
      })
    }
  }
});
</script>

<style scoped lang="scss">
.create__user__div {
  background: #F5F5F5;
  height: 100vh;
  padding-top: 70px;
}
.create__user__div__title h1{
  font-size: 40px;
  font-weight: 800;
  line-height: 48px;
}
.create__inputs div label {
  font-size: 14px;
  font-weight: 400;
}
.create__inputs div {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.create__inputs div input{
  box-shadow: 0px 1px 2px 0px #0000001A;
  background: #FFFFFF;
  border: none;
  outline: none;
  height: 40px;
  width: 380px;
  margin-top: 10px;
  padding-left: 10px;
}
.create__inputs {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 32px;
  margin-top: 50px;
}
.special__inputs__div {
  display: flex !important;
  align-items: center !important;
  flex-direction: inherit !important;
  justify-content: inherit !important;
}
.special__inputs__div input {
  height: 40px !important;
  width: 180px !important;
}
.special__inputs__div div {
  margin-right: 20px;
}
.create__user__div__btn button {
  margin-top: 50px;
}
@media(max-width: 1300px) {
  .create__inputs div input {
    width: 360px;
  }
  .special__inputs__div input {
    width: 160px !important;
  }
}
@media(max-width: 1200px) {
  .create__inputs div input {
    width: 340px;
  }
  .special__inputs__div input {
    width: 150px !important;
  }
}
@media(max-width: 1150px) {
  .create__inputs div input {
    width: 320px;
  }
  .special__inputs__div input {
    width: 145px !important;
  }
}
@media(max-width: 1100px) {
  .create__inputs div input {
    width: 300px;
  }
  .special__inputs__div input {
    width: 135px !important;
  }
}
@media(max-width: 1050px) {
  .create__inputs div input {
    width: 280px;
  }
  .special__inputs__div input {
    width: 125px !important;
  }
}
@media(max-width: 1000px) {
  .create__inputs div input {
    width: 260px;
  }
  .special__inputs__div input {
    width: 115px !important;
  }
}
@media(max-width: 900px) {
  .create__inputs div input {
    width: 240px;
  }
  .special__inputs__div input {
    width: 105px !important;
  }
}
@media(max-width: 850px) {
  .create__inputs div input {
    width: 230px;
  }
  .special__inputs__div input {
    width: 95px !important;
  }
}
@media(max-width: 800px) {
  .create__inputs div input {
    width: 345px;
  }
  .special__inputs__div input {
    width: 145px !important;
  }
  .create__inputs {
    grid-template-columns: 1fr 1fr;
  }
}
@media(max-width: 750px) {
  .create__inputs div input {
    width: 305px;
  }
  .special__inputs__div input {
    width: 135px !important;
  }
}
@media(max-width: 700px) {
  .create__inputs div input {
    width: 280px;
  }
  .special__inputs__div input {
    width: 125px !important;
  }
}
@media(max-width: 650px) {
  .create__inputs div input {
    width: 250px;
  }
  .special__inputs__div input {
    width: 110px !important;
  }
}
@media(max-width: 580px) {
  .create__inputs div input {
    width: 220px;
  }
  .special__inputs__div input {
    width: 100px !important;
  }
}
@media(max-width: 500px) {
  .create__inputs div input {
    width: 350px;
  }
  .special__inputs__div input {
    width: 150px !important;
  }
  .create__inputs {
    grid-template-columns: 1fr;
  }
}
@media(max-width: 400px) {
  .create__inputs div input {
    width: 320px;
  }
  .special__inputs__div input {
    width: 145px !important;
  }
  .create__inputs {
    grid-template-columns: 1fr;
  }
}

</style>
