<template>
  <div>
    <span class="tab"
          :class="{ activeTab: selectedTab === tab }"
          v-for="(tab, index) in tabs"
          :key="index"
          @click="selectedTab = tab">
          {{ tab }}</span>
  
    <div v-show="selectedTab === 'Reviews'">
      <p v-if="!reviews.length">There is no review yet.</p>
      <ul>
        <li v-for="review in reviews" :key="review.index">
          <p>{{ review.name }}</p>
          <p>Rating: {{ review.rating }}</p>
          <p>{{ review.review }}</p>
        </li>
      </ul>
    </div>
    
    <ProductReview  v-show="selectedTab === 'Make a Review'"
                    @review-submitted="addReview" />
    
  </div>
</template>

<script>
import ProductReview from '@/components/ProductReview.vue'

export default {
  name: 'product-tabs',
  components: {
    ProductReview
  },
  props: {
    reviews: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      tabs: ['Reviews', 'Make a Review'],
      selectedTab: 'Reviews'
    }
  },
  methods: {
    addReview(productReview) {
      this.reviews.push(productReview);
    }
  }
}
</script>

<style scoped>

</style>