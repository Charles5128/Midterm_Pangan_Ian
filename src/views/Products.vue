<template>
  <div>
    <h1>Product Management</h1>
    <ProductForm @add-product="addProduct" />
    <ProductList :products="products" @update-product="updateProduct" />
  </div>
</template>

<script>
import ProductForm from '../components/ProductForm.vue'
import ProductList from '../components/ProductList.vue'

export default {
  components: {
    ProductForm,
    ProductList,
  },
  data() {
    return {
      products: [],
    }
  },
  methods: {
    addProduct(product) {
      this.products.push(product)
    },
    updateProduct({ product, index }) {
      this.$set(this.products, index, product)
    },
  },
}
</script>
