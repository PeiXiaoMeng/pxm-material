<script setup>
import { ref } from 'vue'

defineProps({
  name: String,
  size: String,
  type: String,
  children: String,
})

const count = ref(0)

const emit = defineEmits(['handleClick'])

const handleClick = (evt) => {
  console.log(evt);
  emit('click', evt);
}

</script>

<template>
  <button
    :class="`el-button el-button__${size} el-button__${type}`"
    @click="handleClick">
    <span>{{name || '默认'}}</span>
  </button>
</template>

<style lang='less' scoped>
.el-button {
  cursor: pointer;
  outline: none;
  border: 1px solid #dcdfe6;

  &__medium {
    padding: 8px 12px;
    border-radius: 4px;
  }

  &__small {
    padding: 4px 8px;
    border-radius: 3px;
  }

  &__mini {
    padding: 1px 6px;
    border-radius: 3px;
  }

  &__primary {
    background-color: #409eff;
    border-color: #409eff;
    color: #fff;
  }

  &__success {
    background-color: #67c23a;
    border-color: #67c23a;
    color: #fff;
  }

  &__danger {
    background-color: #f56c6c;
    border-color: #f56c6c;
    color: #fff;
  }
}

.el-button:hover {
  opacity: 0.8;
}
</style>
