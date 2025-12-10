<script setup>
const props = defineProps({
  label: {
    type: String,
    required: true
  },
  level: {
    type: String,
    default: 'normal',
    validator: (value) => ['normal', 'warning', 'error'].includes(value)
  }
})

const messageClass = {
  'message': true,
  'message-normal': props.level === 'normal',
  'message-warning': props.level === 'warning',
  'message-error': props.level === 'error'
}
</script>
<template>
  <div :class="messageClass">
    {{ label }}
  </div>
</template>
<style scoped>
.message {
  padding: 1rem;
  margin: 1rem 0;
  border-radius: 4px;
  border-left: 4px solid;
}

.message-normal {
  background-color: #f0f0f0;
  border-left-color: #333;
  color: #333;
}

.message-warning {
  background-color: #fff3cd;
  border-left-color: #ff9800;
  color: #856404;
}

.message-error {
  background-color: #f8d7da;
  border-left-color: #dc3545;
  color: #721c24;
}
</style>