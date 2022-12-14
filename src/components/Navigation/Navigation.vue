<template>
  <div class="navbar">
    <!-- <div class="navbar-logo">
      <div class="navbar-logo-circle"></div>
      <div class="navbar-logo-title">staking PLATFORM</div>
    </div>
    <Button> Connect wallet </Button> -->
  </div>
</template>

<script lang="ts" setup>
// import Button from "../base/Button.vue";
</script>


<style lang="scss" scoped>
.navbar {
  height: 96px;
  padding: 16px 150px;
  background-color: #ffffff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border: 1px solid #d7d8df;
  &-logo {
    display: flex;
    align-items: center;
    &-circle {
      width: 64px;
      height: 64px;
      margin-right: 16px;
      background: #d7d8df;
      border-radius: 50%;
    }
    &-title {
      font-weight: 400;
      font-size: 28px;
      text-transform: uppercase;
      color: #191a1b;
    }
  }
}
</style>


<!--<template>
  <div class="navbar">
    <div class="navbar-logo">
      <div class="navbar-logo-circle"></div>
      <div class="navbar-logo-title">staking PLATFORM</div>
    </div>
    <ButtonMini> Connect wallet </ButtonMini>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ButtonMini from "../Buttons/ButtonMini/ButtonMini.vue";

export default defineComponent({
  name: "NavBar",
  components: {
    ButtonMini,
  },

  setup() {
    return {};
  },
});
</script>


<style lang="scss" scoped>
.navbar {
  height: 96px;
  padding: 16px 150px;
  background-color: #ffffff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border: 1px solid #d7d8df;
  &-logo {
    display: flex;
    align-items: center;
    &-circle {
      width: 64px;
      height: 64px;
      margin-right: 16px;
      background: #d7d8df;
      border-radius: 50%;
    }
    &-title {
      font-weight: 400;
      font-size: 28px;
      text-transform: uppercase;
      // font-feature-settings: "pnum" on, "lnum" on;
      color: #191a1b;
    }
  }
}
</style>