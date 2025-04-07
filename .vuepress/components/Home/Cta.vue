<template>
  <div v-if="config" class="cta-main">
    <h3>{{ config.title }}</h3>
    <p>{{ config.description }}</p>
    <Button
      class="cta-main_button"
      :buttonText="config.url.text"
      :to="this.config.url.link"
    />
  </div>
</template>

<script>
import Button from "../Button.vue";
import config from "../../config";

export default {
  components: { Button },
  data() {
    return {
      config: config.cta,
    };
  },
};
</script>

<style lang="stylus">
@import '../../theme/styles/config.styl'

.cta-main
  color #fff
  display flex
  flex-direction column
  align-items center
  justify-content center
  width 100%
  margin-bottom 3rem

  h3
    font-size clamp(2rem, calc(-.875rem + 1.8vw),8.5rem)
    line-height 28px
    margin-bottom 1rem
    max-width 55rem
    text-align center

  p
    font-size clamp(1rem, calc(-.875rem + 1.8vw),8.5rem)
    line-height 28px
    max-width 55rem
    text-align center
    padding 0 1rem

  &_button
    padding-top 1rem

</style>
