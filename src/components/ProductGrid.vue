<script setup>
    import {productImage} from '../data/products'

    defineProps({items: Array})
    const emit = defineEmits(['select'])
</script>
<template>
    <div class="product-grid">
        <button v-for="item in items" :key="item.classId" class="product-card" @click="emit('select', item)">
            <span class="image-wrap"><img :src="productImage(item)" :alt="item.name"></span>
            <span>{{ item.name }}</span><i>查看系列（{{ item.products.length }}） →</i>
        </button>
    </div>
</template>
