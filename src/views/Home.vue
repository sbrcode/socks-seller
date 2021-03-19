<template>
  <div>
    <SocksSeller/>
    <ProductReview/>
  </div>
</template>

<script>
// @ is an alias to /src
import SocksSeller from '@/components/SocksSeller.vue'
import ProductReview from '@/components/ProductReview.vue'

export default {
  components: {
    SocksSeller,
    ProductReview
  }
}
</script>
