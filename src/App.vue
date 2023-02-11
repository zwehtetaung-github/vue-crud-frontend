<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-primary justify-content-between flex-nowrap flex-row">
      <div class="container">
        <a href="#" class="navbar-brand float-left">Vue Axios Express Mongodb</a>
        <ul class="nav navbar-nav flex-row flex-right">
          <li class="nav-item">
            <router-link class="nav-link mr-5" to="/">Create Student</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/view">View Students</router-link>
          </li>
        </ul>
      </div>
    </nav>
    <div class="container mt-5">
      <router-view/>
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
