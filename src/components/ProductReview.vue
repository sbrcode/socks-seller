<template>
  <div>

    <!-- <h2>Reviews</h2>
    <p v-if="!reviews.length">There is no review yet.</p>
    <ul>
      <li v-for="review in reviews" :key="review">
        <p>{{ review.name }}</p>
        <p>Rating: {{ review.rating }}</p>
        <p>{{ review.review }}</p>
      </li>
    </ul>

    <product-review @review-submitted="addReview"></product-review> -->


    <!-- <form class="review-form" @submit.prevent="onSubmit"> -->
    <form class="review-form">

      <p>
        <label for="name">Name:</label>
        <input id="name" v-model="name" required>
      </p>

      <p>
        <label for="review">Review:</label>
        <textarea id="review" v-model="review" required></textarea>
      </p>

      <p>
        <label for="rating">Rating:</label>
        <select id="rating" v-model.number="rating" required>
          <option>5</option>
          <option>4</option>
          <option>3</option>
          <option>2</option>
          <option>1</option>
        </select>
      </p>

      <p>
        <input type="submit" value="Submit">
      </p>

    </form>
  </div>
</template>

<script>
export default {
  name: 'product-review',
  data() {
    return {
      name: null,
      review: null,
      rating: null,
    }
  }
}
</script>

<style scoped>

</style>