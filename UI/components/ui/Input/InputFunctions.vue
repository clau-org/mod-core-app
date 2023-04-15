<script setup >
    const props = defineProps({
        modelValue: String,
        max: {
            type: Number,
            default: 100,
        },
        label: {
            type: String,
            default: ''
        },
        classIn: {
            type: String,
            default: ''
        }
    });

    const charCount = computed(() => {
        return props.modelValue?.length ?? 0
    }) 

    const isMaxCharsReached = computed(() => {
      return (props.modelValue?.length ?? 0) == props.max;
    })
</script>

<template>
    <div>
        <slot name="top" v-bind="{max, isMaxCharsReached, charCount, label}"></slot>
        <input v-bind="$attrs" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" :maxlength="max" :class="classIn">
        <slot name="bot" v-bind="{max, isMaxCharsReached, charCount, label}"></slot>
    </div>
</template>