<template>
  <header class="navbar">
    <!--      <LaneAbove />-->
    <div class="menu">
      <router-link :to="$localePath" class="home-link logo-gm-events">
        <img class="logo" :src="$withBase(logo)" alt="Logo" />
      </router-link>
      <div class="links">
        <!-- <NavLinks class="can-hide"/> -->
        <div class="can-hide link" v-for="item in this.links" :key="item.link">
          <NavLink :item="item" />
        </div>

        <!-- <AlgoliaSearchBox v-if="isAlgoliaSearch" :options="algolia"/> -->
        <!-- <SearchBox v-else-if="$site.themeConfig.search !== false"/> -->
      </div>
      <div class="menu_submit-event-and-duct-tape-logo">
        <Button
          class="menu_button-submit-event"
          buttonText="Submit Event"
          :to="this.config.submitEventLink"
        />
        <a class="menu_duct-tape-logo" href="https://ducttape.events/" target="_blank">
          <img src='./../public/duct-tape-logo.svg' alt="duct tape logo" height="60" />
        </a>

      </div>
      <SidebarButton @toggle-sidebar="$emit('toggle-sidebar')" />
    </div>
  </header>
</template>

<script>
import SidebarButton from "./SidebarButton.vue";
// import AlgoliaSearchBox from "@AlgoliaSearchBox";
import SearchBox from "./SearchBox.vue";
import NavLink from "./NavLink.vue";
import Button from "../components/Button.vue";
import LaneAbove from "../components/LaneAbove.vue";
import config from "./../config.js";

export default {
  components: {
    SidebarButton,
    NavLink,
    SearchBox,
    // AlgoliaSearchBox,
    Button,
    LaneAbove,
  },
  data() {
    return {
      links: config.themeConfig.nav,
      config: config,
    };
  },
  computed: {
    algolia() {
      return (
        this.$themeLocaleConfig.algolia || this.$site.themeConfig.algolia || {}
      );
    },
    isAlgoliaSearch() {
      return this.algolia && this.algolia.apiKey && this.algolia.indexName;
    },
    logo() {
      return require("./../public/logo_gm_events.svg");
    },
  },
};
</script>

<style lang="stylus">
@import './styles/config.styl'

.menu
  padding 0.1rem $sidesPadding
  display flex
  align-items center
  justify-content space-between

  &_button-submit-event
    display none

.navbar
  line-height $navbarHeight - 1.4rem
  position relative
  a, span, img
    display inline-block
  .logo
    height $navbarHeight - 1.8rem
    min-width $navbarHeight - 1.4rem
    margin-right 0
    vertical-align top
  .site-name
    font-size 1.3rem
    font-weight 600
    color #fff
    position relative
  .links
    font-size 0.9rem
    display flex
    .link
      padding 0 1.5rem
      color white

@media (max-width: $MQMobile)
  .navbar
    padding 1.3rem 1.5rem
    .links
      right 3.5rem
    .logo
      height 2rem
      min-width 2rem

    .can-hide
      display none

@media (min-width: $MQMobile)
  .menu
    height 87px
    padding 0.1rem $sidesPaddingDesktop

    &_button-submit-event
      display block

.menu_submit-event-and-duct-tape-logo
  display flex
  align-items center
  gap 1.5rem

.menu_duct-tape-logo
  display flex !important

.logo-gm-events
  width 223px

</style>
