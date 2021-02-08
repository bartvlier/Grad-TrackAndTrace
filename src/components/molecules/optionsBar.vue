<template>
  <div class="wrapper">
    <div class="options">
      <stage ref="stagePicked" stage="picked" class="arrow"></stage>
      <stage ref="stagePacked" stage="packed" class="arrow"></stage>
      <stage ref="stageShipped" stage="shipped" class="arrow"></stage>
      <stage ref="stageAccepted" stage="accepted" class="arrow"></stage>
      <stage ref="stageSorted" stage="sorted" class="arrow"></stage>
      <stage ref="stageDelivery" stage="delivery" class="arrow"></stage>
      <stage ref="stageDelivered" stage="delivered"></stage>
    </div>

    <div class="button-group">
      <button @click="setPreset1" :class="{ active: isActive1 }">
        Weinig updates
      </button>
      <button @click="setPreset2" :class="{ active: isActive2 }">
        Standaard updates
      </button>
      <button @click="setPreset3" :class="{ active: isActive3 }">
        Alle updates
      </button>
    </div>
  </div>
</template>

<script>
import stage from "@/components/atoms/stage.vue";

export default {
  name: "optionsBar",
  components: {
    stage
  },
  data() {
    return {
      isActive1: false,
      isActive2: false,
      isActive3: false
    };
  },
  methods: {
    setPreset1() {
      const {
        stagePicked,
        stagePacked,
        stageShipped,
        stageAccepted,
        stageSorted,
        stageDelivery,
        stageDelivered
      } = this.$refs;

      stagePicked.setState(false);
      stagePacked.setState(false);
      stageShipped.setState(true);
      stageAccepted.setState(false);
      stageSorted.setState(false);
      stageDelivery.setState(true);
      stageDelivered.setState(true);
      this.isActive1 = this.isActive1 ? false : true;
      this.isActive2 = false;
      this.isActive3 = false;
    },
    setPreset2() {
      const {
        stagePicked,
        stagePacked,
        stageShipped,
        stageAccepted,
        stageSorted,
        stageDelivery,
        stageDelivered
      } = this.$refs;

      stagePicked.setState(false);
      stagePacked.setState(false);
      stageShipped.setState(true);
      stageAccepted.setState(true);
      stageSorted.setState(false);
      stageDelivery.setState(true);
      stageDelivered.setState(true);
      this.isActive1 = false;
      this.isActive2 = this.isActive2 ? false : true;
      this.isActive3 = false;
    },
    setPreset3() {
      const {
        stagePicked,
        stagePacked,
        stageShipped,
        stageAccepted,
        stageSorted,
        stageDelivery,
        stageDelivered
      } = this.$refs;

      stagePicked.setState(true);
      stagePacked.setState(true);
      stageShipped.setState(true);
      stageAccepted.setState(true);
      stageSorted.setState(true);
      stageDelivery.setState(true);
      stageDelivered.setState(true);
      this.isActive1 = false;
      this.isActive2 = false;
      this.isActive3 = this.isActive3 ? false : true;
    }
  }
};
</script>

<style lang="scss">
.wrapper {
  width: 60%;
  background-color: white;
  box-shadow: 0px 32px 64px rgba(17, 17, 17, 0.08);
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 50px;
  border-radius: 20px;
  .options {
    width: 90%;
    display: flex;
    justify-content: space-between;
    align-items: top;
    margin-bottom: 40px;

    .arrow {
      position: relative;
      &:after {
        content: "";
        background-image: url("../../assets/arrow.svg");
        width: 16px;
        height: 15px;
        position: absolute;
        z-index: 1;
        left: 110px;
        top: 45px;
      }
    }
  }
  .button-group {
    button {
      padding: 10px;
      font-size: 14px;
      line-height: 21px;
      font-weight: 400;
      background-color: transparent;
      border: 2px solid #0379e7;
      color: #0379e7;
      margin: 0px 10px;
      border-radius: 10px;
      cursor: pointer;

      &:hover {
        background-color: #0379e7;
        color: white;
      }

      &.active {
        background-color: #0379e7;
        color: white;
      }
    }
  }
}
</style>
