<template>
    <div>
        <!-- Display component as such passing any props you need to-->
        <HomeSection1 @activity-panel-selected="showActivityPanelMethod" @items-panel-selected="showItemsPanelMethod" />
        <HomeNFTDisplay v-if="showItemsPanel" />
        <h1 v-if="showActivityPanel">No activities to show</h1>
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <HomeSection2 />
    </div>
</template>

<script>
//Import your components
import HomeSection1 from '@/components/homepage/HomeSection1.vue'
import HomeSection2 from '@/components/homepage/HomeSection2.vue'
import HomeNFTDisplay from '@/components/homepage/HomeNFTDisplay.vue'

export default {
  data() {
    return {
      showItemsPanel: true,
      showActivityPanel: false,
    }
  },
  name: 'Homepage',
  components: {
    HomeSection1,
    HomeSection2, // Add your components
    HomeNFTDisplay
  },
  methods: {
    showItemsPanelMethod(){
      this.showItemsPanel = true;
      this.showActivityPanel = false;
    },
    showActivityPanelMethod(){
      this.showItemsPanel = false;
      this.showActivityPanel = true;
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
