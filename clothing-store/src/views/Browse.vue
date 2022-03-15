<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Red')" href="#" class="pure-menu-link">Red</a></li>
      <li class="pure-menu-item"><a @click="select('Black')" href="#" class="pure-menu-link">Black</a></li>
      <li class="pure-menu-item"><a @click="select('Gray & White')" href="#" class="pure-menu-link">Gray and White</a></li>
      <li class="pure-menu-item"><a @click="select('Other Colors')" href="#" class="pure-menu-link">Other Colors</a></li>
    </ul>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse-View',
  components: {
    ProductList
  },
  data() {
    return {
      color: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.color === this.color);
    }
  },
  methods: {
    select(color) {
      this.color = color;
    }
  }
}
</script>

<style scoped>
.pure-menu-link
{
    text-decoration: none;
    color:white;
    font-weight: bold;
    font-size: 14pt;
}
</style>