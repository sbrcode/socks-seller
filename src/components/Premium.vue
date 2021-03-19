<template>
  <Product :premium="premium" />
</template>

<script>
import Product from '@/components/Product.vue'

export default {
  name: 'premium',
  components: {
    Product
  },
  data() {
    return {
      premium: true
    }
  }
}
</script>

<style scoped>

</style>