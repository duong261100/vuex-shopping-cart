<template>
  <div>
      <h1>Your Cart</h1>

      <cart-items
        v-for="product in items"
        :key="product.id"
        :product="product"
      >
        {{ product.name }}
      </cart-items>

      <payment-card />
  </div>
</template>

<script>
import CartItems from '../components/cart/CartItem.vue'
import PaymentCard from '../components/cart/PaymentCard.vue'
export default {
  components: { CartItems, PaymentCard },
  computed: {
    items() {
      return this.$store.getters.cartItems
    }
  }
}
</script>

<style>

</style>
