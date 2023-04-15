<script setup >

    const props = defineProps({
        theme: {
            type: String,
            default: '',
        },
    });
    
</script>

<template>
    <div>
        <UiInputThemeDanger v-if="theme == 'danger'" :is="componenteActual" v-bind="$attrs" />
        <UiInputTheme       v-else                  :is="componenteActual" v-bind="$attrs" />
    </div>
</template>
  