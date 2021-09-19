<template>
  <div id="app">
   
    <NavigationMobile />
    <div class="content" :class="{'open':showNav}">
      <div class="top-bar">
        <div id="navigation-icon" v-if="mobileView"
          @click="showNav = !showNav">
          <i class="fas fa-bars"></i>
        </div>
        <Navigation v-if="!mobileView" />
      </div>
      <Content />
      <Galery v-if="!mobileView"/>
      <GaleryMobile v-if="mobileView"/>
    </div>
  
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import NavigationMobile from "./components/NavigationMobile.vue";
import Content from "./components/Content.vue";
import Galery from "./components/Galery.vue";
import GaleryMobile from "./components/GaleryMobile.vue";

export default {
  data: () => {
    return {
      mobileView: true,
      showNav: false
    };
  },
  methods: {
    handleView() {
      this.mobileView = window.innerWidth <= 990;
    }
  },
  components: {
    Navigation,
    NavigationMobile,
    Content,
    Galery,
    GaleryMobile
  },
  created() {
    this.handleView();
    window.addEventListener('resize', this.handleView);
  }
};
</script>

<style lang="scss">
@import url("https://use.fontawesome.com/releases/v5.9.0/css/all.css");
* {
  font-size: 1rem;
color: #efefef;
}
body {
  width: 100%;
  margin: 0;
  top:0;
min-height: 285vh;
    bottom:0;
  padding: 0;
  font-family: "Segoe UI", Tahoma;
  background-color: #FF8C00;
}
#app {
  position: relative;
  width: calc(100% - 20px);
min-height: 285vh;
  padding: 10px;
  color: #333;
  overflow: hidden;
}

.top-bar {
  display: flex;
  width: 100%;
}
#navigation-icon {
  padding: 10px 10px 20px;
  margin-right: 10px;
  cursor: pointer;
  i {
    font-size: 2rem;
  }
}
.content {
  position: absolute;
  top: 10px;
  width: 100%;
    padding: 20px;
  background-color: rgb(20, 19, 19);
    box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  transition: 1s transform cubic-bezier(0,.12,.14,1);
}
.open {
  transform: translateX(300px);
}
</style>