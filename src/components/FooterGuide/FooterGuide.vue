<template>
  <div class="footer_guide border-1px">
    <span v-for="(menu,index) in menus" :key="index" class="guide_item" :class="{on:'/'+menu.path === $route.path}"
          @click="goTo(menu.path)">
      <span class="item_icon">
        <i class="iconfont" :class="menu.iconName"></i>
      </span>
      <span>{{menu.name}}</span>
    </span>
  </div>
</template>

<script>
  // import xx from 'xxx'

  export default {
    components: {},
    props: [],
    data () {
      return {
        menus: [
          {
            path: 'msite',
            iconName: 'icon-waimai',
            name: '外卖'
          },
          {
            path: 'search',
            iconName: 'icon-search',
            name: '搜索'
          },
          {
            path: 'order',
            iconName: 'icon-dingdan',
            name: '订单'
          },
          {
            path: 'profile',
            iconName: 'icon-geren',
            name: '我的'
          }
        ]
      }
    },
    computed: {},
    watch: {},
    methods: {
      goTo (path) {
        this.$router.replace(path)
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/mixins.styl"
  .footer_guide //footer
    top-border-1px(#e4e4e4)
    position fixed
    z-index 100
    left 0
    right 0
    bottom 0
    background-color #fff
    width 100%
    height 50px
    display flex

    .guide_item
      display flex
      flex 1
      text-align center
      flex-direction column
      align-items center
      margin 5px
      color #999999

      &.on
        color #02a774

      span
        font-size 12px
        margin-top 2px
        margin-bottom 2px

        .iconfont
          font-size 22px
</style>
