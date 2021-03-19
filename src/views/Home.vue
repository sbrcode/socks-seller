<template>
  <div>
    <Premium />
    <ProductReview />
  </div>
</template>

<script>
// @ is an alias to /src
import Premium from '@/components/Premium.vue'
import ProductReview from '@/components/ProductReview.vue'

export default {
  components: {
    Premium,
    ProductReview
  }
}
</script>
