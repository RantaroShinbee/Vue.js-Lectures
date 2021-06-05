<template>
  <div>
    <the-home-page> </the-home-page>
  </div>
</template>

<script>
// import label-collection.json
import LabelStorage from './asset/resources/label-storage.json';
import DummyHomeData from './dummy_data/dummy-home-data.json';
// import components
import TheHomePage from './components/page/the-home-page.vue';

export default {
  components: {
    TheHomePage,
  },
  data() {
    return {
      marketingItemList: [
        {
          id: 1,
          heading: 'Heading',
          description:
            'Some representative placeholder content for the first slide of the carousel.',
        },
        {
          id: 2,
          heading: 'Heading',
          description:
            'Some representative placeholder content for the first slide of the carousel.',
        },
        {
          id: 3,
          heading: 'Heading',
          description:
            'Some representative placeholder content for the first slide of the carousel.',
        },
      ],
    };
  },
  provide() {
    return {
      labelStorage: LabelStorage,
      dummyHomeData: DummyHomeData,
    };
  },
};
</script>

<style>
</style>
