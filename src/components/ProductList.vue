<template>
  <div>
    <ul>
      <li v-for="(product, index) in products" :key="index">
        <span>{{ product.name }} - ${{ product.price }}</span>
        <button @click="editProduct(index)">Edit</button>
      </li>
    </ul>
    <div v-if="isEditing">
      <h3>Edit Product</h3>
      <ProductForm @add-product="updateProduct" :product="selectedProduct" />
    </div>
  </div>
</template>

<script>
import ProductForm from './ProductForm.vue'

export default {
  components: {
    ProductForm,
  },
  props: {
    products: Array,
  },
  data() {
    return {
      isEditing: false,
      selectedProduct: null,
      selectedIndex: null,
    }
  },
  methods: {
    editProduct(index) {
      this.isEditing = true
      this.selectedProduct = { ...this.products[index] }
      this.selectedIndex = index
    },
    updateProduct(product) {
      this.$emit('update-product', { product, index: this.selectedIndex })
      this.isEditing = false
      this.selectedProduct = null
      this.selectedIndex = null
    },
  },
}
</script>
