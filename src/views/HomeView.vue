<template>
  <div class="home">
    <div class="product-cards-container">
      <product-description-drawer
        :product="product"
        :active="active.product_drawer"
        @close-product-drawer="closeProductDrawer()"
      />

      <product-card
        v-for="product in items"
        :key="product.id"
        :product="product"
        @viewProduct="viewProduct($event)"
      />
    </div>
  </div>
</template>

<script>
import items from '../data/items.js'
import ProductCard from '../components/products/ProductCard.vue'
import ProductDescriptionDrawer from '../components/products/ProductDescriptionDrawer.vue'
export default {
  name: 'HomeView',
  components: {
    ProductCard,
    ProductDescriptionDrawer
  },
  data() {
    return {
      items: items,
      product: null,
      active: {
        product_drawer: false
      }
    }
  },
  methods: {
    viewProduct(product) {
      this.product = product
      this.active.product_drawer = true
    },
    closeProductDrawer() {
      this.active.product_drawer = false
    }
  }
}
</script>

<style lang="scss" scoped>
  .product-cards-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding-top: 30px;
  }
</style>
