<template>
  <div class="home">
    <div id="gif-box">
      <router-link to="/about"
        ><img src="../../images/gif_2.gif"
      /></router-link>

      <h3>Klikni na kutiju levatu</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
};
</script>

<style>
.home {
  height: 100vh;
}

#gif-box {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
}

.home img {
  width: 100%;
}
</style>
