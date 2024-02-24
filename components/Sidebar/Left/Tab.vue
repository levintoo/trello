<template>
    <NuxtLink :to
        :class="defaultTransition"
        class="flex items-center p-3 text-black rounded-full w-min hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white"
        >

        <div class="w-6 h-6 text-dark">
            <slot name="icon" />
        </div>

        <div :class="textClasses" class="hidden ml-4 text-xl xl:block">
            <slot name="name" />
        </div>

    </NuxtLink>
</template>
<script setup>
const { defaultTransition } = useTailwindConfig()

const props = defineProps({
  active: {
    type: Boolean,
    default: false
  },
  to: {
    type: String,
    default: '#',
  }
})

const textClasses = computed(() => props.active ? 'font-semibold' : 'font-normal')
</script>