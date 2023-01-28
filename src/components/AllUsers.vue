<template>
  <div class="all__users__div">
    <div class="container">
      <div class="all__users__div__title__and__btn df_jscpb_ai">
        <h1>Users</h1>
        <router-link to="/create" class="base__btn df_jsc_ai">Create user</router-link>
      </div>
      <div class="all__users__cards">
        <router-link v-for="(user, index) in users" :to="{name:'user', params:{id:user.id}}" class="users__cards" tag="div">
          <h3>{{user.name}}</h3>
          <p class="user__username">@{{user.username}}</p>
          <p class="user__email">{{user.email}}</p>
          <p class="user__phone">{{user.phone}}</p>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "AllUsers",
  props: ['id'],
  data(){
    return {
      users: null
    }
  },
  methods: {
    getUsers() {
      axios.get('https://jsonplaceholder.typicode.com/users/')
          .then(response => {
            this.users = response.data
          })
          .catch(error => {
            console.log(error)
          });
    }
  },
  mounted() {
    this.getUsers()
  }
}
</script>

<style scoped>
  .users__cards {
    height: 120px;
    width: 380px;
    background: #FFFFFF;
    box-shadow: 0px 1px 2px 0px #0000001A;
    padding: 30px;
  }
  .all__users__div {
    background: #F5F5F5;
    padding-top: 70px;
    padding-bottom: 20px;
  }
  .all__users__cards {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
    padding-top: 50px;
  }
  .all__users__cards div {
    cursor: pointer;
  }
  .user__email {
    padding-top: 20px;
  }
  .user__username {
    padding-top: 5px;
  }
  .user__phone {
    padding-top: 5px;
  }
  @media(max-width: 1400px) {
    .users__cards {
      width: 370px;
    }
    .all__users__div {
      height: 100vh;
    }
  }
  @media(max-width: 1300px) {
    .users__cards {
      width: 310px;
    }
    .all__users__div {
      height: 100vh;
    }
  }
  @media(max-width: 1100px){
    .users__cards {
      width: 275px;
    }
    .all__users__div {
      height: 100vh;
    }
  }
  @media(max-width: 1050px){
    .users__cards {
      width: 275px;
      padding: 20px;
    }
    .all__users__div {
      height: 100vh;
    }
  }
  @media(max-width: 1000px){
    .users__cards {
      width: 255px;
      padding: 20px;
    }
    .all__users__div {
      height: 100vh;
    }
  }
  @media (max-width: 950px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 360px;
      padding: 30px;
    }
  }
  @media (max-width: 870px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 330px;
      padding: 25px;
    }
  }
  @media (max-width: 800px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 327px;
      padding: 20px;
    }
  }
  @media (max-width: 750px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 293px;
      padding: 20px;
    }
  }
  @media (max-width: 700px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 280px;
      padding: 20px;
    }
  }
  @media (max-width: 630px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 263px;
      padding: 15px;
    }
  }
  @media (max-width: 670px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 263px;
      padding: 15px;
    }
  }
  @media (max-width: 600px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 240px;
      padding: 15px;
    }
  }
  @media (max-width: 570px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
    }
    .users__cards {
      width: 225px;
      padding: 15px;
    }
    .users__cards h3 {
      font-size: 17px;
    }
    .users__cards p {
      font-size: 14px;
    }
    .user__email{
      padding-top: 35px;
    }
  }
  @media (max-width: 530px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }
    .users__cards {
      width: 205px;
      padding: 15px;
    }
    .users__cards h3 {
      font-size: 17px;
    }
    .users__cards p {
      font-size: 14px;
    }
    .user__email{
      padding-top: 35px;
    }
  }
  @media (max-width: 500px) {
    .all__users__cards {
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }
    .users__cards {
      width: 195px;
      padding: 15px;
    }
    .users__cards h3 {
      font-size: 15px;
    }
    .users__cards p {
      font-size: 11px;
    }
    .user__email{
      padding-top: 40px;
    }
  }
  @media (max-width: 470px) {
    .all__users__cards {
      grid-template-columns: 1fr;
      gap: 10px;
    }
    .users__cards {
      width: 380px;
      padding: 30px;
    }
    .users__cards h3 {
      font-size: 21px;
    }
    .users__cards p {
      font-size: 18px;
    }
    .user__email{
      padding-top: 25px;
    }
  }
  @media (max-width: 450px) {
    .all__users__cards {
      grid-template-columns: 1fr;
      gap: 10px;
    }
    .users__cards {
      width: 340px;
      padding: 30px;
    }
    .users__cards h3 {
      font-size: 21px;
    }
    .users__cards p {
      font-size: 18px;
    }
    .user__email{
      padding-top: 25px;
    }
  }
  @media (max-width: 400px) {
    .all__users__cards {
      grid-template-columns: 1fr;
      gap: 10px;
    }
    .users__cards {
      width: 320px;
      padding: 30px;
    }
    .users__cards h3 {
      font-size: 21px;
    }
    .users__cards p {
      font-size: 18px;
    }
    .user__email{
      padding-top: 25px;
    }
  }
  @media (max-width: 360px) {
    .all__users__cards {
      grid-template-columns: 1fr;
      gap: 10px;
    }
    .users__cards {
      width: 320px;
      padding: 15px;
    }
    .users__cards h3 {
      font-size: 21px;
    }
    .users__cards p {
      font-size: 18px;
    }
    .user__email{
      padding-top: 25px;
    }
  }
  </style>