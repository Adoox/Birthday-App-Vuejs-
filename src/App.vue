<template>
  <div id="app">
    <div id="nav">
      <div id="navbar">
        <router-link to="/">Home</router-link>
      </div>
    </div>
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}

#nav {
  padding: 10px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#nav {
  background-color: rgba(0, 0, 0, 0.335);
  display: flex;
  justify-content: center;
}
</style>
