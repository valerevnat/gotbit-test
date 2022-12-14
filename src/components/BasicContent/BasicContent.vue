<template>
  <div class="basic-content">
    <div>
      <div class="basic-content-apy">
        <div class="basic-content-apy-text">110% APY</div>
        <div class="basic-content-apy-help">
          <div class="basic-content-apy-help-btn" @click="handlerTooltipApy">
            <img src="../../resorces/img/help-active.svg" alt="help" />
          </div>
        </div>
        <div class="basic-content-apy-tooltip">
          <TooltipContainer v-model:showTooltip="hideTooltipAPY">
            <div class="basic-content-apy-help-text">
              Текст с подсказкой Текст с подсказкой Текст с подсказкой Текст с
              подсказкой Текст с подсказкой
            </div>
          </TooltipContainer>
        </div>
      </div>
      <div class="basic-content-tvl">
        <div class="basic-content-tvl-text">
          <div class="basic-content-tvl-text-left">TVL</div>
          <div>300$</div>
        </div>
        <div class="basic-content-tvl-help">
          <div class="basic-content-apy-help-btn" @click="handlerTooltipTvl">
            <img src="../../resorces/img/help-inactive.svg" alt="help" />
          </div>
        </div>
        <div class="basic-content-tvl-tooltip">
          <TooltipContainer v-model:showTooltip="hideTooltipTVL">
            <div class="basic-content-tvl-help-text">Текст подсказка TVL</div>
          </TooltipContainer>
        </div>
      </div>
    </div>

    <div class="basic-content-img">
      <img src="../../resorces/img/basic-main-screen.png" alt="help" />
    </div>
    <div class="basic-content-btn">
      <ButtonsMain @click="handlerShow"> Connect wallet </ButtonsMain>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import TooltipContainer from "../Tooltips/Tooltip.vue";
import ButtonsMain from "../Buttons/ButtonMain/ButtonsMain.vue";

export default defineComponent({
  name: "BasicContent",
  components: {
    TooltipContainer,
    ButtonsMain,
  },
  props: ["handlerShowModal", "handlerContentModal"],

  setup(props) {
    const hideTooltipAPY = ref<boolean>(false);
    const hideTooltipTVL = ref<boolean>(false);

    const handlerTooltipApy = () => {
      hideTooltipAPY.value = !hideTooltipAPY.value;
    };

    const handlerTooltipTvl = () => {
      hideTooltipTVL.value = !hideTooltipTVL.value;
    };

    const handlerShow = () => {
      console.log("click");
      props.handlerContentModal("basic");
      props.handlerShowModal();
    };

    return {
      hideTooltipAPY,
      hideTooltipTVL,
      handlerTooltipApy,
      handlerTooltipTvl,
      handlerShow,
    };
  },
});
</script>

<style lang="scss" scoped>
.basic-content {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  justify-content: space-between;

  &-apy {
    display: flex;
    align-items: center;

    &-text {
      font-weight: 700;
      font-size: 40px;
      color: #000000;
      margin-right: 8px;
    }

    &-help {
      &-btn {
        cursor: pointer;
        img {
          width: 24px;
          height: 24px;
        }
      }
    }
    &-tooltip {
      position: absolute;
      left: 100%;
    }
  }

  &-tvl {
    display: flex;
    align-items: center;
    margin-top: 16px;
    &-text {
      display: flex;
      font-size: 24px;
      color: #000000;
      margin-right: 8px;
      &-left {
        color: #9799a1;
        margin-right: 24px;
      }
    }

    &-help {
      &-btn {
        cursor: pointer;
      }
    }
    &-tooltip {
      position: absolute;
      left: 100%;
    }
  }
}
</style>
