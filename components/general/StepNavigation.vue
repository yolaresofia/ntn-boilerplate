<template>
  <div class="stepNav fixed flex flex-col justify-center z-10">
    <div @click="navigateToStep(0)">
      <img v-if="this.$store.state.video === 0" class="lg:w-12" src="~/assets/step-nav-arrows.svg" alt="" />
      <img v-else src="~/assets/navigation-circle.svg" alt="" />
    </div>
    <img src="~/assets/dots.svg" alt="" />
    <div @click="navigateToStep(1)">
      <img v-if="this.$store.state.video === 1" class="lg:w-12" src="~/assets/step-nav-arrows.svg" alt="" />
      <img v-else src="~/assets/navigation-circle.svg" alt="" />
    </div>
    <img src="~/assets/dots.svg" alt="" />
    <div @click="navigateToStep(2)">
      <img v-if="this.$store.state.video === 2" class="lg:w-12" src="~/assets/step-nav-arrows.svg" alt="" />
      <img v-else src="~/assets/navigation-circle.svg" alt="" />
    </div>
    <img src="~/assets/dots.svg" alt="" />
    <div @click="navigateToStep(3)">
      <img v-if="this.$store.state.video === 3" class="lg:w-12" src="~/assets/step-nav-arrows.svg" alt="" />
      <img v-else src="~/assets/navigation-circle.svg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'StepNavigation',
  methods: {
    navigateToStep(step) {
      window.scrollTo(0, 250 * step)
      console.log((window.innerHeight / 3) * step)
    //   window.scrollTo(0, 300)
      setTimeout(() => {
        this.$store.commit('stepNavigation', step)
      }, 100)
    },
  },
}
</script>

<style>
.stepNav {
  max-height: 100px;
  right: 3%;
  top: 40%;
}
.stepNav img {
  margin: auto;
}
</style>