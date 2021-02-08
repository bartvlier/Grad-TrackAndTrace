<template>
  <div
    class="stage-wrapper"
    :class="{ active: active }"
    @click="setState(!active)"
  >
    <div class="icon">
      <img
        v-if="stage === 'picked'"
        src="@/assets/forklift-solid.svg"
        alt="Barcode-Icon"
      />
      <img
        v-if="stage === 'packed'"
        src="@/assets/box-solid.svg"
        alt="Barcode-Icon"
      />
      <img
        v-if="stage === 'shipped'"
        src="@/assets/postnl.svg"
        alt="Barcode-Icon"
      />
      <img
        v-if="stage === 'accepted'"
        src="@/assets/box-check-solid.svg"
        alt="Barcode-Icon"
      />
      <img
        v-if="stage === 'sorted'"
        src="@/assets/conveyor-belt-alt-solid.svg"
        alt="Barcode-Icon"
      />
      <img
        v-if="stage === 'delivery'"
        src="@/assets/shipping-fast-solid.svg"
        alt="Barcode-Icon"
      />
      <img
        v-if="stage === 'delivered'"
        src="@/assets/check-solid.svg"
        alt="Barcode-Icon"
      />
    </div>
    <div class="description">
      <p v-if="stage === 'picked'">Je bestelling wordt verzameld</p>
      <p v-if="stage === 'packed'">Je bestelling wordt verpakt</p>
      <p v-if="stage === 'shipped'">
        Je bestelling is meegegeven met de bezorgdienst
      </p>
      <p v-if="stage === 'accepted'">Je pakket is geaccepteerd</p>
      <p v-if="stage === 'sorted'">Je pakket is gesorteerd</p>
      <p v-if="stage === 'delivery'">De bezorger is onderweg</p>
      <p v-if="stage === 'delivered'">Je pakket is bezorgd</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "stage",
  props: {
    stage: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      active: false
    };
  },
  methods: {
    setState(value) {
      this.active = value;
    }
  }
};
</script>

<style lang="scss" scoped>
.stage-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;

  .icon {
    width: 100px;
    height: 100px;
    background-color: #c4c4c4;
    border-radius: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

    img {
      width: 50px;
    }
  }
  .description {
    width: 100px;
    font-size: 11px;
    text-align: center;
  }

  &.active {
    .icon {
      background: #0379e7;
    }
  }
}
</style>
