<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/category1">Category 1</router-link></li>
          <li><router-link to="/category2">Category 2</router-link></li>
        </ul>
      </nav>
    </header>

    <main>
      <router-view></router-view>
    </main>

    <footer>
      <p>Shopping Website &copy; 2025</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
}

header {
  background-color: #42b983;
  padding: 10px;
  text-align: center;
}

nav ul {
  list-style: none;
  padding: 0;
}

nav ul li {
  display: inline;
  margin-right: 15px;
}

nav a {
  color: white;
  text-decoration: none;
}

footer {
  text-align: center;
  padding: 20px;
  background-color: #f1f1f1;
}
</style>
