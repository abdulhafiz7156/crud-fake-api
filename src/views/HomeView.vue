<template>
  <AllUsers />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CreateUser from '@/components/CreateUser.vue';
import AllUsers from "@/components/AllUsers.vue"; // @ is an alias to /src

export default defineComponent({
  name: 'HomeView',
  components: {
    AllUsers,
    CreateUser,
  },
});
</script>
