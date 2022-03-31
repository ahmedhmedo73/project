<template>
  <ecommerce :darkTheme="darkTheme" />
  <nav-bar
    :darkTheme="darkTheme"
    @changeTheme="changeTheme"
    @toggleSideBar="toggleSideBar"
  />
  <side-bar :darkTheme="darkTheme" />
</template>

<script>
import sideBar from "./components/sideBar.vue";
import navBar from "./components/nav.vue";
import ecommerce from "./components/ecommerce.vue";

export default {
  name: "App",
  data() {
    return {
      darkTheme: false,
      show:false
    };
  },
  created() {
    window.addEventListener('resize', this.changeScreen);
  },
  components: {
    sideBar,
    navBar,
    ecommerce,
  },
  methods: {
    changeTheme() {
      this.darkTheme = !this.darkTheme;
    },
    toggleSideBar() {
      this.showSideBar = !this.showSideBar;
      console.log("work");
    },
    changeScreen(){
      this.screen = window.innerWidth;
    }
  }
  ,provide(){
    return {
      screen: 0,
      showSideBar: true
    }
  }
};
</script>

<style lang="scss">
body {
  margin: 0;
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  box-sizing: border-box;
}
</style>
