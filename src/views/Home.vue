<template>
  <div class="home">
    <div id="desktop-view">
      <div id="alert-box">
        <h2>Aplikacija nije dostupna na desktop i laptop računalima!</h2>
      </div>
    </div>
    <div id="mobile-view">
      <div id="gif-box">
        <router-link to="/about"
          ><img src="../../images/gif_2.gif"
        /></router-link>

        <h3>Your text goes here!</h3>
      </div>
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

@media only screen and (max-width: 430px) {
  #desktop-view {
    display: none;
  }
}

@media only screen and (min-width: 430px) and (max-width: 960px) {
  #desktop-view {
    display: none;
  }
}
@media only screen and (min-width: 961px) {
  #mobile-view {
    display: none;
  }
}
</style>
