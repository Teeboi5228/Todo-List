<template>
  <div class="preloader-container">
    <img
      src="../assets/icon-logo-i.png"
      class="animate__animated animate__heartBeat animate__slower animate__infinite"
      alt=""
    />
  </div>
</template>

<script>
export default {
  name: "PreloaderVue",
};
</script>

<style scoped>
.preloader-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  background-color: #c6c6c6b3;
  transition: all 0.5s ease-in-out;
}

.preloader-container img {
  width: 50px;
  height: 50px;
}
</style>
