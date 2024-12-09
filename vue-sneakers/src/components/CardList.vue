<script setup>
import Card from './Card.vue'

defineProps({
    items: Array,
})

const emit = defineEmits('addToFavorite', 'addToCart')
</script>

<template>
    <div class="grid grid-cols-4 gap-5 mt-10" v-auto-animate>
        <Card
        v-for="item in items"
        :key="item.id"
        :title="item.title" 
        :id="item.id"
        :price="item.price" 
        :imageUrl="item.imageUrl"
        :onClickAdd="() => emit('addToCart', item)"
        :onClickFavorite="() => emit('addToFavorite', item)"
        :isFavorite="item.isFavorite"
        :isAdded="item.isAdded"
        />
    </div>
</template>