<script setup >
    
</script>

<template>
    <div class="relative">
        <UiInputFunctions v-bind="$attrs" classIn="pl-2 bg-blue-200 mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50" >
            <template #top="{ label }" >
                <label for="input" class="block font-medium text-gray-700">{{label}}</label>
            </template>
            <template #bot="{ charCount, max }" >
                <div class="absolute bottom-0 right-3">
                    <span class="text-gray-500">{{ charCount }}/{{ max }}</span>
                </div>
            </template>
        </UiInputFunctions>
    </div>
</template>