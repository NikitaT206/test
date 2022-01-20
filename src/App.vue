<template>
  <div id="nav">
    <router-link to="/">Пиво</router-link> |
    <router-link to="/about">Профиль</router-link>
  </div>
  <router-view/>
</template>

<style>
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding: 0;
  text-align: center;
  min-height: 100vh;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  overflow: scroll;
}

#nav {
  padding-top: 50px;
  display: flex;
  gap: 30px;
  margin: 0 auto;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  font-size: 20px;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
