<template>
  <div class="home">
    <div class="container-fluid p-0 m-0">
      <div v-show="showCoverPage" class="coverDisplay">
        <CoverPageVue />
      </div>
      <div class="content-container" v-show="!showCoverPage">
        <AdsProjectVue />
      </div>
    </div>
  </div>
</template>

<script>
import AdsProjectVue from "@/components/AdsProject.vue";
import CoverPageVue from "../components/CoverPage.vue";
export default {
  name: "HomeView",
  components: {
    CoverPageVue,
    AdsProjectVue,
  },
  data() {
    return {
      showCoverPage: true,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showCoverPage = false;
    }, 4000);
  },
};
</script>

<style scoped>
.preloader,
.coverDisplay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  z-index: 1000;
}
</style>
