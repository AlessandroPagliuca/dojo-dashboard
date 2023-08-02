<template>
  <div class="container-fluid d-flex">

    <div class="menu-sx p-3">
      <h4 class="pb-4 text-start">- Dashbool -</h4>
      <!--Info user-->
      <div class="d-flex justify-content-between align-items-center pb-4">
        <div style="width: 50px; height: 50px;border: 4px solid white; border-radius: 50%; overflow: hidden;">
          <img class="img-fluid" src="../public//img//avatar_2.jpg" alt="#">
        </div>
        <!--Name and surname user-->
        <div class="">
          <p>Welcome</p>
          <h6>Mario Rossi</h6>
        </div>
      </div>
      <!--Links-->
      <h6 class="text-uppercase pb-2 my-text-with-line">general</h6>
      <!--link home-->
      <div class="pt-4 pb-4">
        <div class="d-flex align-items-center justify-content-start">
          <i class="fa-solid fa-home icon-menu-sx"></i>
          <p class="link-menu-sx text-center pe-4" @click="toggleMenu">Home</p>
        </div>
        <ul class="menu-links no-style-ul" v-show="showMenu">
          <li class="link-menu-sx"><a href="#">Dashboard 1</a></li>
          <li><a href="#">Dashboard 2</a></li>
          <li><a href="#">Dashboard 3</a></li>
        </ul>
      </div>
    </div>

    <div class="menu-dx">
      <div class="menu-dx-top p-3 d-flex justify-content-between align-items-center">
        top
      </div>

      <div class="menu-dx-bot p-3 justify-content-center">
        <RouterView></RouterView>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      showMenu: false,
    }
  },
  methods: {
    toggleMenu() {
      this.showMenu = !this.showMenu;
    }
  }
}
</script>

<style lang="scss" scoped>
@use './assets/partials/variables' as *;

.b {
  border: 1px solid black;
}

.menu-sx {
  width: 200px;
  height: 100vh;
  background-color: $color-blue;
  color: white;

}

.menu-dx {
  width: calc(100% - 200px);
  height: 100vh;

  .menu-dx-top {
    height: 50px;
    background-color: $color-grey;
  }

  .menu-dx-bot {
    height: calc(100% - 50px);
    background-color: $color-light-grey;
    overflow-y: auto;
  }
}

.my-text-with-line {
  border-bottom: 2px solid white;
}

.no-style-ul {
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: center;

  li {
    width: 100%;
  }
}

.icon-menu-sx {
  width: 25px;
  font-size: 20px;
}

.link-menu-sx {
  width: calc(100% - 25px);
}
</style>