<script setup>
import axios from 'axios'
import {ref, onMounted} from 'vue'

import CardList from '@/components/CardList.vue';

const favorites = ref({})

onMounted(async () => {
    try {
        const {data} = await axios.get('https://dc00a0d015dd71d4.mokky.dev/favorites');

        favorites.value = data.map((obj) => obj.item)
    } catch (err) {
        console.log(err)
    }
})

</script>

<template>
<div>
    <h1 font-bounded>Мои зкладки</h1>
    <CardList :items="favorites"/>
</div>
</template>