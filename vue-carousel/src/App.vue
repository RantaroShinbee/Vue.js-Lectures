<template>
  <div>
    <the-home-page> </the-home-page>
  </div>
</template>

<script>
// import label-collection.json
import LabelStorage from './asset/resource/label-storage.json';
// import components
import TheHomePage from './components/page/the-home-page.vue';

export default {
  components: {
    TheHomePage
  },
  data() {
    return {
      labelStorage: LabelStorage,
    }
  },
  provide() {
    return {
      labelStorage: this.labelStorage
    }
  }
};
</script>

<style>
</style>
