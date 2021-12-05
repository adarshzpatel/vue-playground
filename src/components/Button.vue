<template>
  <button class="lv-button" v-bind="$attrs" :class="themeClass"  >
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
  },
  computed: {
    themeClass(){
      return {
        'lv-primary-btn': this.color == 'primary',
        'lv-secondary-btn': this.color == 'secondary',
        'lv-info-btn' : this.color == 'info',
      }
    }
  }
}
</script>

<style lang="scss">
.lv-primary-btn{
  background: var(--primary);
  &:hover{
    background: var(--primary-light);
  }
  &:active{
    background: var(--primary-dark);
  }
}

.lv-secondary-btn{
  background: var(--secondary);
  &:hover{
    background: var(--secondary-light);
  }
  &:active{
    background: var(--secondary-dark);
  } 
}

.lv-info-btn{
  background: var(--info);
  &:hover{
    background: var(--info-light);
  }
  &:active{
    background: var(--info-dark);
  } 
}

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