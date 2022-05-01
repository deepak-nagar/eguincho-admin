<template>
  <!-- CART DROPDOWN -->

  <div class="ml-4 mr-6 mt-1" />
</template>

<script>
import VuePerfectScrollbar from "vue-perfect-scrollbar";

export default {
  components: {
    VuePerfectScrollbar,
  },
  data() {
    return {
      settings: {
        // perfectscrollbar settings
        maxScrollbarLength: 60,
        wheelSpeed: 0.6,
      },
    };
  },
  computed: {
    // CART DROPDOWN
    cartItems() {
      return this.$store.state.eCommerce.cartItems.slice().reverse();
    },
    scrollbarTag() {
      return this.$store.getters.scrollbarTag;
    },
  },
  methods: {
    removeItemFromCart(item) {
      this.$store.dispatch("eCommerce/toggleItemInCart", item);
    },
  },
};
</script>
