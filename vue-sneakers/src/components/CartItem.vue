<script setup>
    const emit = defineEmits(['onClickRemove'])

    defineProps({
        id: Number,
        title: String,
        imageUrl: String,
        price: Number,
    })
</script>

<template>
    <div class="flex items-center p-4 gap-4 border border-slate-100 rounded-xl">
        <img class="w-16 h-16" :src="imageUrl" :alt="title"/>

        <div class="flex flex-col flex-1">
            <slate>{{ title }}</slate>

            <div class="flex justify-between mt-2">
                <b class="flex-1">{{ price }} руб.</b>
                <img 
                @click="emit('onClickRemove')"
                class="opacity-40 hover:opacity-100 cursor-pointer transition" 
                src="/close.svg"
                />
            </div>
        </div>
    </div>
</template>