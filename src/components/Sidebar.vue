<template>
 <div class="container" :class="{'show': showSidebar}">
    <div class="control">
      <i class="fas fa-angle-double-right" @click="showNav"></i>
    </div>
    <div class="navigation-icons">
       <i class="fas fa-home"></i>
      <i class="fas fa-camera-retro"></i>
      <i class="fas fa-user-circle"></i>
      <i class="fas fa-comment-dots"></i>
      <i class="fas fa-info-circle"></i>
    </div>
    <div class="navigation-links">
      <transition-group>
        <div v-show="showLink" key="1">Home</div>
        <div v-show="showLink" key="2">Portfolio</div>
        <div v-show="showLink" key="3">About Me</div>
        <div v-show="showLink" key="4">Contact</div>
        <div v-show="showLink" key="5">FAQ</div>
      </transition-group>
    </div>
  </div>
</template>

<script>
  export default {
    data: () => {
      return {
        showSidebar: false,
        showLink: false
      }
    },
    methods: {
      showNav() {
        if(this.showSidebar) {
          this.showLink = false;
          setTimeout(() => {
            this.showSidebar = false;
          }, 500);
        }
        else {
          this.showSidebar = true;
          setTimeout(() => {
            this.showLink = true;
          }, 500);
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  position: absolute;
  top: 0;
  left: 0;
  width: 50px;
  padding: 10px;
  min-height: calc(100vh - 20px);
  background-color: rgba(64,88,16, .8);
  border: solid #fff;
  border-width: 0 1px 0 0;
  z-index: 999;
  transition: all .5s ease-in-out;
}
.control {
  display: flex;
  justify-content: center;
  align-items: center;
   width: 50px;
  margin-bottom: 10px;
}
i {
  font-size: 2rem;
  cursor: pointer;
  transition: all .5s ease-in-out;
}
.show {
  width: 200px;
}
.control, .i {
  color: #fff;
}
.navigation-icons {
  color: #fff;
}
.navigation-icons {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 50px;
  float: left;
}
i {
  font-size: 2rem;
  padding: 10px 0;
  cursor: pointer;
  transition: all .5s ease-in-out;
}
.navigation-links {
  padding-top: 14px;
  float: left;
}
div {
  font-size: 1.35rem;
  padding-left: 10px;
  margin-bottom: 18px;
  cursor: pointer;
}
</style>
