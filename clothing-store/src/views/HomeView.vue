<template>
  <div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Home-View',
  components: {
    ProductList
  },
  data() {
    return {
      searchText: '',
    } 
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.price.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
  },
}
</script>

<style scoped>

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 100px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 400px;
}
</style>