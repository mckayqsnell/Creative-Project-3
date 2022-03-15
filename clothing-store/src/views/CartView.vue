<template>
  <div>
    <div v-if="hasItems">
      <div
        class="product"
        v-for="(product, index) in cartItems"
        :key="`product-${index}`"
      >
        <div class="image">
          <img :src="'/images/adidas/' + product.image" />
        </div>
        <div class="info">{{ product.name }}</div>
        <div class="price">{{ product.price }}</div>
        <div class="action">
          <button class="auto" v-on:click="removeFromCart(index)">
            Remove item
          </button>
        </div>
      </div>
    </div>
    <div v-else>
      You don't have any items in your cart.
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
.product 
{
  display: grid;
  grid-template-columns:1fr 1fr 1fr 1fr;
  grid-auto-rows: minmax(50px, auto);
  border: solid black;
  padding: 8px;
  margin: 15px;
  border-radius: 20px;
  background:black;
  color:white;
}

.product img 
{
  height: 100px;
}

.info 
{
  font-weight: bolder;
  color: white;
}

button {
  color:white;
  background:black;
}
</style>
