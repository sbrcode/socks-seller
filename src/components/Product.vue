<template>
  <div class="socks">

    <div class="product-image">
      <img :src="image">
    </div>

    <div class="product-info">
      
      <h1>{{ title }}</h1>
      <p v-if="inStock">In Stock</p>
      <p v-else>Out of Stock</p>
      <p>Shipping: {{ shipping }}</p>

      <ul>
        <li v-for="detail in details" :key="detail">{{ detail }}</li>
      </ul>

      <div v-for="(variant, index) in variants"
            :key="variant.variantId"
            class="color-circle"
            :style="{ backgroundColor: variant.variantColor }"
            @mouseover="updateProduct(index)"
            >
      </div>

      <button v-on:click="addToCart"
              :disabled="!inStock"
              :class="{ disabledButton: !inStock }"
              >
        Add to Cart
      </button>

    </div>
  </div>
</template>

<script>
export default {
  name: 'product',
  props: {
    premium: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      brand: "So Socket",
      product: "Socks",
      selectedVariant: 0,
      details: ["80% cotton", "20% polyester", "Gender-neutral"],
      variants: [
        {
          variantId: 2234,
          variantColor: "green",
          variantImage: require("@/assets/socks_green.jpg"),
          variantQuantity: 10,
        },
        {
          variantId: 2235,
          variantColor: "blue",       
          variantImage: require("@/assets/socks_blue.jpg"),
          variantQuantity: 0,
        }
      ],
    }
  },
  methods: {
    addToCart() {
      this.$emit('add-to-cart', this.variants[this.selectedVariant].variantId);
    },
    updateProduct(index) {
      this.selectedVariant = index;
    }
  },
  computed: {
    title() {
      return this.brand + ' ' + this.product;
    },
    image() {
      return this.variants[this.selectedVariant].variantImage;
    },
    inStock() {
      return this.variants[this.selectedVariant].variantQuantity;
    },
    shipping() {
      if (this.premium) {
        return "Free"
      }
      return 2.99
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
