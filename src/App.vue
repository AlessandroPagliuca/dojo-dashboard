<template>
  <div class="container-fluid d-flex">

    <div class="menu-sx p-3">
      menu sx
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
</style>