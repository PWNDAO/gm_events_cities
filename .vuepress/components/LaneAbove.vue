<template>
  <div class="lane-above">
    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;Powered by &nbsp;
      <img :src="$withBase(ductTapeLogo)" alt="duct tape logo" />
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;1000 attendees
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;Powered by &nbsp;
      <img :src="$withBase(ductTapeLogo)" alt="duct tape logo" />
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;In-person Events & Parties
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;Powered by &nbsp;
      <img :src="$withBase(ductTapeLogo)" alt="duct tape logo" />
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;Online & In-person Events
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;Powered by &nbsp;
      <img :src="$withBase(ductTapeLogo)" alt="duct tape logo" />
    </div>

    <div class="lane-above__box">
      <img :src="$withBase(greenDot)" alt="green dot" />
      &nbsp;3000 attendees
    </div>

  </div>
</template>

<script>

export default {
  name: "LaneAbove",
  computed: {
    greenDot () {
      return require('./../public/green_dot.svg')
    },
    ductTapeLogo () {
      return require(`./../public/duct-tape-logo.svg`)
    }
  },
};
</script>

<style scoped>
.lane-above {
  background: black;
  align-items: center;
  justify-content: center;
  display: flex;
  overflow: hidden;
  white-space: nowrap;
  height: 56px;
}

.lane-above__box {
  line-height: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  font-family: 'Helvetica', sans-serif;
  margin: 0 1.5rem;
}

</style>
