<template>
  <div>
    <user-interface-navigation-bar></user-interface-navigation-bar>
    <user-interface-sliding-section></user-interface-sliding-section>
    <user-interface-marketing-item></user-interface-marketing-item>
  </div>
</template>

<script>
// import components
import UserInterfaceNavigationBar from '../user-interface/ui-navigation-bar.vue';
import UserInterfaceSlidingSection from '../user-interface/ui-sliding-section.vue';
import UserInterfaceMarketingItem from '../user-interface/ui-marketing-item.vue';

export default {
  components: {
    UserInterfaceNavigationBar,
    UserInterfaceSlidingSection,
    UserInterfaceMarketingItem,
  },
};
</script>
<style>
</style>