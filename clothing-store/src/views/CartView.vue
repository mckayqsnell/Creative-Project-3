<template>
  <div>
    <div v-if="hasItems">
      <div
        class="product"
        v-for="(product, index) in cartItems"
        :key="`product-${index}`"
      >
        <div class="info">{{ product.name }}</div>
        <div class="color">{{product.color}}</div>
        <div class="price">-{{ product.price }}</div>
      </div>
    </div>
    <div v-else>
      You don't have any Favorites
    </div>
  </div>
</template>

<script>
export default {
  name: "Cart-View",
  data() {
    return {
      formatter: 90,
    };
  },
  computed: {
    cartItems() 
    {
      return this.$root.$data.cart;
    },

    hasItems() 
    {
      return this.$root.$data.cart.length !== 0;
    },
  },
  methods: 
  {
    removeFromCart(index) {
      console.log(this.cartItems[index].name);
      this.cartItems.splice(index, 1);
    },
  }
};
</script>

<style scoped>
.product{
  padding: 20px;
  background-color: #750101;
  margin: 5px;
}
.info
{
  font-size: 30px;
}

.price{
  font-style: italic;
  padding-top: 1%;
}

.color {
    padding-top: .5%;
    font-size: 20px;
}
</style>
