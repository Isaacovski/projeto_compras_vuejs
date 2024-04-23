<script setup>
  defineprops({
    title:{
      type:String,
      required: true
    },
    visible: {
      type: boolean,
      required: true
    },
  })

  defineEmits(['update:visible'])
</script>

<template>
  <div class="panel-wrap">
    <div class="panel">
      <div>
        <button class="btn error-outline">
        close
      </button>
      <h2>{{ title }}</h2>
      </div>
      <slot name="content"></slot>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.panel{
  position: absolute;
}
</style>