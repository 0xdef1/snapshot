<template>
  <div
    class="border-top border-bottom border-md rounded-0 rounded-md-2 mb-4 block-bg"
  >
    <h4
      v-if="title"
      class="px-4 pt-3 border-bottom d-block bg-gray-dark rounded-top-0 rounded-md-top-2"
      style="padding-bottom: 12px"
    >
      {{ title }}
      <UiCounter v-if="counter" :counter="counter" class="ml-1" />
      <a
        v-if="icon"
        @click="$emit('submit')"
        class="float-right text-gray"
        style="padding-top: 2px"
      >
        <Icon :name="icon" size="22" />
      </a>
    </h4>
    <div :class="!slim && 'p-4'">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: ['title', 'counter', 'slim', 'icon'],
  emits: ['submit']
};
</script>
