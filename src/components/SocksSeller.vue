<template>
  <div class="product">
    <div class="product-image">
      <img src="image">
    </div>
    <div class="product-info">
      <h1>{{ product }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      product: 'Socks',
      image: '@/assets/socks_geren.jpg'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
