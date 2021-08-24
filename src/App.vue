<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link :to="{ name: 'About'}">About</router-link> |
    <router-link :to="{ name: 'Jobs'}">Jobs</router-link>
  </div>

  <button @click="redirect">Redirect</button>
  <button @click="forward">Go Forward</button>
  <button @click="back">Go Back</button>

  <router-view/>
</template>

<script>
  export default {
    methods: {
      redirect() {
        this.$router.push({ name: 'Home' })
      },
      forward() {
        this.$router.go(1)
      },
      back() {
        this.$router.go(-1)
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  border-radius: 10px;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: white;
  background-color: tomato;
  font-weight: bold;
  padding: 10px;
}
</style>
