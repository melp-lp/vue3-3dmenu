<template>
<ul class="vue3-3dmenu">
  <li 
    v-for="(menu, idx) in list" 
    :key="idx" 
    :style="`--i:${list.length - idx}`"
    @click="onClickMenu(menu)">
    {{ menu.name }}
  </li>
</ul> 
</template>

<script setup>
const emit = defineEmits(['click-menu']);
defineProps(
  {
    list: {
      type: Array,
      default: () => []
    }
  }
);

const onClickMenu = (menu) => {
  emit('click-menu', menu);
}
</script>

<style lang="less">
.vue3-3dmenu {
  list-style: none;
  padding: 0;
  margin: 0;
  width: 200px;
  margin-left: 300px;
  margin-top: 200px;
  transform: skewY(-15deg);
  user-select: none;

  li {
    width: 100%;
    height: 40px;
    line-height: 40px;
    font-size: 14px;
    background: #DDD;
    border-bottom: 1px solid #FFF;
    position: relative;
    cursor: pointer;
    z-index: var(--i);
    transition: .5s;

    &::before {
      content: '';
      width: 40px;
      height: 100%;
      position: absolute;
      left: -40px;
      top: 0px;
      background: #CCC;
      transform: skewY(45deg);
      transform-origin: right;
      transition: .5s;
    }

    &::after {
      content: '';
      width: 100%;
      height: 40px;
      position: absolute;
      left: 0px;
      top: -40px;
      background: #EEE;
      transform-origin: bottom;
      transform: skewX(45deg);
      transition: .5s;
    }

    &:hover {
      transform: translate(-20px, 0px);
      background: #09F;
      color: #FFF;
      &::before {
        background: rgb(3, 127, 209);
      }
      &::after {
        background: #0099ffD0;
      }
    }
  }
}
</style>