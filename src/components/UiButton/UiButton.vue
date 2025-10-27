<template>
  <button :class="$style.button" :data-layout="props.layout" :disabled="props.isDisabled" :type="props.type">
    <slot></slot>
  </button>
</template>

<script setup lang="ts">
interface IProps {
  layout?: 'primary' | 'secondary';
  type?: 'submit' | 'button';
  isDisabled?: boolean;
}

const props = withDefaults(defineProps<IProps>(), {
  layout: 'primary',
  type: 'button',
});
</script>

<style module lang="scss">
.button {
  position: sticky;
  display: flex;
  gap: 8px;
  align-items: center;
  justify-content: center;
  width: 120px;
  height: 60px;
  padding: 16px 32px;
  font-size: 1rem;
  line-height: 1.5;
  color: var(--color-white);
  background: var(--color-primary);
  border-radius: 16px;

  &[data-layout='secondary'] {
    color: var(--color-primary);
    background-color: var(--color-secondary);
    border-color: var(--color-primary);
  }
}
</style>
