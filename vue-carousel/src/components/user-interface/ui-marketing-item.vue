<template>
  <div>
    <div 
      class="col-lg-4"
      v-for="marketingItem in itemList"
      :key="marketingItem.id"
      :head="marketingItem.heading"
      :description="marketingItem.description">
      <svg
        class="bd-placeholder-img rounded-circle"
        width="140"
        height="140"
        xmlns="http://www.w3.org/2000/svg"
        role="img"
        aria-label="Placeholder: 140x140"
        preserveAspectRatio="xMidYMid slice"
        focusable="false"
      >
        <title>Placeholder</title>
        <rect width="100%" height="100%" fill="#777" />
        <text x="50%" y="50%" fill="#777" dy=".3em">140x140</text>
      </svg>

      <h2>{{ head }}</h2>
      <p>{{ description }}</p>
      <user-interface-view-detail-button></user-interface-view-detail-button>
    </div>
  </div>
</template>
<script>
  import UserInterfaceViewDetailButton from './ui-view-detail-button.vue';

export default {
  inject: ['dummyHomeData'],
  components: {
    UserInterfaceViewDetailButton
  },
  data() {
    return {
      itemList: this.dummyHomeData.marketingItemList
    }
  }
}
</script>
<style></style>