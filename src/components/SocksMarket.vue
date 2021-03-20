<template>
  <div>
    
    <div class="cart">
      <p>Cart({{ cart.length }})</p>
    </div>

    <Product :premium="premium" @add-to-cart="updateCart" />

    <ProductTabs :reviews="reviews" />

  </div>
</template>

<script>
import Product from '@/components/Product.vue'
import ProductTabs from '@/components/ProductTabs.vue'

export default {
  name: 'socks-market',
  components: {
    Product,
    ProductTabs
  },
  data() {
    return {
      premium: false,
      cart: [],
      reviews: [],
    }
  },
  methods: {
    updateCart(id) {
      this.cart.push(id);
    },
    // addReview(productReview) {
    //   this.reviews.push(productReview);
    // }
  }
}
</script>

<style scoped>

</style>