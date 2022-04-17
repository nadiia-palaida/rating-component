<template>
  <div class="container container-rating">
    <div class="rating-modal">
      <div v-if="!isSubmit" class="rating-modal-select">
        <div class="circle-button circle-button-star">
          <Icon src="star" color="#FC7614"/>
        </div>

        <h1 class="rating-modal-title title">
          How did we do?
        </h1>

        <p class="rating-modal-description text">
          Please let us know how we did with your support request. All feedback is appreciated to help us improve our
          offering!
        </p>

        <the-select :options="options" v-model="activeRating" class="rating-modal-options"/>

        <button @click="submit" class="rating-modal-submit button">SUBMIT</button>
      </div>

      <div v-else class="rating-modal-thanks">
        <div class="rating-modal-thanks-img">
          <img src="~/assets/img/thanks.png" alt="thanks">
        </div>

        <div class="rating-modal-thanks-selected">
          You selected {{ activeRating }} out of {{ options.length }}
        </div>

        <div class="rating-modal-thanks-title title">
          Thank you!
        </div>

        <div class="rating-modal-thanks-text text">
          We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in
          touch!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Icon from "./Icon";
import TheSelect from "./form/the-select";

export default {
  name: "rating",
  components: {TheSelect, Icon},
  data() {
    return {
      activeRating: 5,
      isSubmit: false,

      options: [
        {
          value: 1,
          label: 1,
        },
        {
          value: 2,
          label: 2,
        },
        {
          value: 3,
          label: 3,
        },
        {
          value: 4,
          label: 4,
        },
        {
          value: 5,
          label: 5,
        },
      ]
    }
  },
  methods: {
    submit() {
      this.isSubmit = true
    }
  }
}
</script>

<style scoped>

</style>
