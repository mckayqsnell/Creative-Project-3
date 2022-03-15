<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="../images/logo_ccexpress.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="../images/globe.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="../images/love.png">
          <p>{{cartCount}} items</p>
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
    cartCount() {
      return this.$root.$data.cart.length;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;
  background: rgb(71, 59, 59);
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

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
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
</style>
