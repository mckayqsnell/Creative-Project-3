<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="../images/logo.jpeg">
      <div class = "wussup">
        <h2>McJokes</h2>
      </div>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse"> 
          <p>About</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <p>Favorites</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class = "footer">
    <div class = "github">
      <a href = "https://github.com/mckayqsnell/Creative-Project-3">Source</a>
    </div>
    <div class = "text">
      <h6> By McKay Snell &amp; Thys Hansen</h6>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'App',
  computed: {
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;
  background: rgb(0, 0, 0);
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #e23737;
}

#brand img {
  height: 150px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
  font-size: 30px;
  text-decoration: none
}

a:link {
  text-decoration: none;
}

a:visited {
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

a:active {
  text-decoration: none;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

.footer 
{
  margin-left:-100px !important;
  position:fixed;
  bottom:0;
  width: 100%;
  height: 60px;
  background-color: #750101 !important;
}

.github a {
  text-decoration: none;
  color:white;
}
.text {
  color:white;
}

.wussup{
  color:#8e1919
}
</style>
