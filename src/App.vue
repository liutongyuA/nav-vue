<template>
  <div id="app">
    <Site></Site>
  </div>
</template>

<script>
import Site from "@/components/Site";
export default {
  name: "App",
  components: {
    Site,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
}
*:before,
*:after {
  box-sizing: border-box;
}
a {
  color: inherit;
  text-decoration: none;
}
#app {
  height: 100vh;
  background-image: url(./assets/wallhaven.jpg);
  background-position: center center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  background-color: #464646;
  /* position:absolute; */
  overflow: hidden;
  /* display: flex; */
}
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
</style>
