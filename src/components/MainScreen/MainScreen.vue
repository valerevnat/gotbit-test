<template>
  <div class="main-screen">
    <div class="main-screen-title">
      <div class="main-screen-title-left">{{ title }}</div>
      <div class="main-screen-title-right">Staking</div>
    </div>
    <div class="main-screen-content">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts" setup>
const title = ref<string>("Flexible");
</script>

<style lang="scss" scoped>
@import "../../assets/variables.scss";

.main-screen {
  &-title {
    display: flex;
    justify-content: center;
    align-items: center;
    &-left,
    &-right {
      color: $main-color;
      font-weight: 900;
      font-size: 64px;
      letter-spacing: -0.5px;
      margin-right: 24px;
    }
    &-right {
      color: #000000;
    }
  }
  &-content {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px 0 40px 0;
    margin-top: 32px;
    width: 949px;
    height: 705px;
    background: #ffffff;
    border-radius: 24px;
  }
}
</style>

<!-- <template>
  <div class="main-screen">
    <div class="main-screen-title">
      <div class="main-screen-title-left">{{ title }}</div>
      <div class="main-screen-title-right">Staking</div>
    </div>
    <div class="main-screen-content">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainScreen",
  components: {},
  setup() {
    const title = ref<string>("Flexible");

    return {
      title,
    };
  },
});
</script>

<style lang="scss" scoped>
@import "../../assets/variables.scss";

.main-screen {
  &-title {
    display: flex;
    justify-content: center;
    align-items: center;
    &-left,
    &-right {
      color: $main-color;
      font-weight: 900;
      font-size: 64px;
      letter-spacing: -0.5px;
      margin-right: 24px;
    }
    &-right {
      color: #000000;
    }
  }
  &-content {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px 0 40px 0;
    margin-top: 32px;
    width: 949px;
    height: 705px;
    background: #ffffff;
    border-radius: 24px;
  }
}
</style>

