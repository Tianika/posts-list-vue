<script setup>
import IconSearch from './icons/IconSearch.vue'

defineProps({
  modelValue: {
    type: String
  }
})
defineEmits(['update:modelValue'])
</script>

<template>
  <div class="search-input">
    <div class="search-input__icon">
      <IconSearch fill="var(--color-border)" width="25" height="25" />
    </div>
    <input
      class="search-input__input"
      type="text"
      :value="modelValue"
      placeholder="Filter by author..."
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>

<style lang="scss">
.search-input {
  display: flex;
  border: 2px solid var(--color-border);
  border-radius: 5px;
  background-color: var(--color-card);

  &__icon {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 5px 10px;
  }

  &__input {
    border: none;
    outline: 2px solid var(--color-border);
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    padding: 5px 10px;

    &:focus {
      outline: 3px solid var(--color-input-shadow);
    }

    &::placeholder {
      color: var(--color-border);
    }
  }
}
</style>
