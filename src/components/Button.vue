<template>
  <button class="lv-button" v-bind="$attrs" :class="color"  >
    <slot></slot>  
  </button>  
</template>

<script>
export default{
  name:'Button',
  props:{
    color:{
      type: String,
      default: 'primary'
    }
  }
}
</script>

<style lang="scss">

.lv-button {
    box-shadow: none !important;
    padding: 12px 20px !important;
    white-space: nowrap;
    border: none;
    border-radius: 4px;
    font-size: medium;
    font-weight: 500;
    color: #fffffe;
  }
</style>