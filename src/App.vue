<template>
  <h1>Router Overview</h1>
  <div class="div-router">
    <button @click="replacePage('/pageA')">Replace Page A</button>
    <button @click="replacePage('/pageB')">Replace Page B</button>
    <button @click="replacePage('/pageC')">Replace Page C</button>
  </div>
  <div class="div-router">
    <button @click="goToPage('/pageA')">Go To Page A</button>
    <button @click="goToPage('/pageB')">Go To Page B</button>
    <button @click="goToPage('/pageC')">Go To Page C</button>
  </div>
  <div class="div-router">
    <router-link to="/pageA">Page A</router-link>
    <router-link to="/pageB">Page B</router-link>
    <router-link to="/pageC">Page C</router-link>
    <router-link :to="{ name: 'user', params: { userId: 1 } }"
      >User</router-link
    >
  </div>
  <div class="div-router">
    <button @click="goToUser">Go To User</button>
  </div>
  <router-view></router-view>
</template>

<script>
export default {
  name: 'App',
  methods: {
    goToPage(route) {
      this.$router.push(route);
    },
    replacePage(route) {
      this.$router.replace(route);
    },
    goToUser() {
      this.$router.push({ name: 'user', params: { userId: 2 } });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.div-router {
  display: flex;
  justify-content: space-around;
}
</style>
