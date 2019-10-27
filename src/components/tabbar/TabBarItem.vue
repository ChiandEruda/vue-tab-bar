<template>
    <div class="tab-bar-item">
        <slot name="item-icon"></slot>
        <slot name="item-text"></slot>
    </div>
</template>

<script>
export default {
    name: 'TabBarItem'
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
</style>