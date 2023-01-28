<template>
    <div v-if="this.activeUser" class="user__div">
      <div class="container">
        <div class="user__title__name df">
          <h1>{{user.name}}</h1> <sup>@{{user.username}}</sup>
        </div>
        <div class="user__data">
          <div class="user__email">
            <h4>Email</h4>
            <p>{{user.email}}</p>
          </div>
          <div class="user__email">
            <h4>Phone</h4>
            <p>{{user.phone}}</p>
          </div>
          <div class="user__email">
            <h4>Website</h4>
            <p>{{user.website}}</p>
          </div>
          <div class="user__email">
            <h4>Company</h4>
            <p>{{user.company.name}}</p>
          </div>
          <div class="user__email">
            <h4>Address</h4>
            <p>{{user.address.street}}, {{user.address.suite}}, {{user.address.zipcode}}</p>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
  name: "UserData",
  props: ['id'],
  data(){
    return {
      user: null,
      activeUser: false
    }
  },
  methods: {
    getUser(){
      axios.get(`https://jsonplaceholder.typicode.com/users/${this.id}`)
          .then(response => {
            this.user = response.data
            this.activeUser = true
          })
          .catch(error => {
            console.log(error)
          });
    }
  },
  mounted() {
    this.getUser()
  }
}
</script>

<style scoped>
.user__div {
  padding-top: 70px;
  background: #F5F5F5;
  height: 100vh;
}
.user__data {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  padding-top: 50px;
}
.user__data p {
  padding-top: 10px;
}
.user__data div {
  margin-bottom: 40px;
}
.user__title__name h1 {
  margin-right: 10px;
}
@media (max-width: 1400px) {
  .user__title__name h1 {
    font-size: 50px;
  }
  .user__title__name sup {
    font-size: 18px;
  }
  .user__data h4 {
    font-size: 22px;
  }
  .user__data p {
    font-size: 20px;
  }
}
@media (max-width: 900px) {
  .user__title__name h1 {
    font-size: 40px;
  }
  .user__title__name sup {
    font-size: 16px;
  }
  .user__data h4 {
    font-size: 20px;
  }
  .user__data p {
    font-size: 18px;
  }
  .user__data div {
    margin-right: 15px;
  }
}
@media (max-width: 700px) {
  .user__title__name h1 {
    font-size: 40px;
  }
  .user__title__name sup {
    font-size: 16px;
  }
  .user__data h4 {
    font-size: 20px;
  }
  .user__data p {
    font-size: 18px;
  }
  .user__data div {
    margin-right: 15px;
  }
}
@media (max-width: 600px) {
  .user__title__name h1 {
    font-size: 45px;
  }
  .user__title__name sup {
    font-size: 18px;
  }
  .user__data h4 {
    font-size: 22px;
  }
  .user__data p {
    font-size: 20px;
  }
  .user__data {
    grid-template-columns: 1fr 1fr;
  }
  .user__data div {
    padding-right: 20px;
  }
}
@media (max-width: 500px) {
  .user__title__name h1 {
    font-size: 35px;
  }
  .user__title__name sup {
    font-size: 18px;
  }
  .user__data h4 {
    font-size: 22px;
  }
  .user__data p {
    font-size: 20px;
  }
  .user__data {
    grid-template-columns: 1fr 1fr;
  }
  .user__data div {
    padding-right: 20px;
  }
}
@media (max-width: 450px) {
  .user__title__name h1 {
    font-size: 30px;
  }
  .user__title__name sup {
    font-size: 16px;
  }
  .user__data h4 {
    font-size: 20px;
  }
  .user__data p {
    font-size: 18px;
  }
  .user__data {
    grid-template-columns: 1fr 1fr;
  }
  .user__data div {
    padding-right: 20px;
  }
}
@media (max-width: 400px) {
  .user__title__name h1 {
    font-size: 40px;
    margin-bottom: 10px;
  }
  .user__title__name {
    display: block;
  }
  .user__title__name sup {
    font-size: 17px;
  }
  .user__data h4 {
    font-size: 22px;
  }
  .user__data p {
    font-size: 20px;
  }
  .user__data {
    grid-template-columns: 1fr;
  }
  .user__data div {
    padding-top: 10px;

  }
}

</style>