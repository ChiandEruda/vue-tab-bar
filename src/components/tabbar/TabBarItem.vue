<template>
    <div class="tab-bar-item" @click="clickItem">
        <div v-if='!isActive'><slot name="item-icon"></slot></div>
        <div v-else><slot name="item-icon-active"></slot></div>
        <div :style="activeStyle"><slot name="item-text"></slot></div>
    </div>
</template>

<script>
export default {
    name: 'TabBarItem',
    props: {
      path: String,
      activeColor: {
        type: String,
        default: 'red',
      }
    },
    data() {
      return {
        // isActive: false,
      }
    },
    computed: {
      isActive() {
        console.log(this.$route.path.indexOf(this.path))
        return !this.$route.path.indexOf(this.path)
      },
      activeStyle() {
        return this.isActive? {color: this.activeColor} : {} 
      }
    },
    methods: {
      clickItem() {
        this.$router.replace(this.path)
      }
    },
}
</script>

<style>
  .tab-bar-item {
    flex: 1;
    height: 49px;
    text-align: center;
    font-size: 14px;
  }

  .tab-bar-item img {
      margin-top: 3px;
      margin-bottom: 2px;
      width: 24px;
      height: 24px;
      vertical-align: middle;
  }

  .active {
    color: #d81e06;
  }
</style>