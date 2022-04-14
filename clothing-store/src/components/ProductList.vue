<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}</h1>
        <p>{{product.color}}</p>
      </div>

      <div class="price">
        <p><i>-{{product.price}}</i></p>
        <button class="auto" v-on:click="addToCart(product)">Add to Favorites</button>
        <hr>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
  },
  
  methods: 
  {
      addToCart(product) 
      {
          console.log("add to favorites", product);
          this.$root.$data.cart.push(product);
      }
  }
}
</script>

<style scoped>

.products {
  background-color: #750101;
  padding: 15px;
}
.product
{
  margin: 5px;
}

hr{
 background-color: black;
}
</style>