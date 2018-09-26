<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

    <button v-on:click="logout">Logout</button>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import firebase from 'firebase/app'
import 'firebase/auth'

export default {
  name: 'home',
  data: function () {
    return {}
  },
  methods: {
    logout: function () {
      firebase.auth().signOut().then(() => {
        this.$router.replace('login')
      })
    }
  },
  components: {
    HelloWorld
  }
}
</script>
