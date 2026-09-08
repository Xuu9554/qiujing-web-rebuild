<script setup>
    import {computed, ref, watch} from 'vue'
    import {productImage} from '../data/products'

    const props = defineProps({items: Array, selected: Object})
    const emit = defineEmits(['select'])
    const active = ref(props.selected || props.items?.[0] || null)
    const preview = ref(null)

    watch(() => props.selected, value => {
        if (value) active.value = value
    })
    watch(() => props.items, value => {
        if (!active.value && value?.length) active.value = value[0]
    })
    const products = computed(() => active.value?.products || [])
    const choose = item => {
        active.value = item
        preview.value = null
        emit('select', item)
    }
</script>
<template>
    <section class="page-hero">
        <div class="shell"><p class="eyebrow">PRODUCT RANGE</p><h1>产品展示</h1><p>探索求精水暖与卫浴产品系列。</p></div>
    </section>
    <main class="shell section catalog-layout">
        <aside class="category-list" aria-label="产品分类">
            <h2>产品分类</h2>
            <button v-for="item in items" :key="item.classId" :class="{active: active?.classId === item.classId}" @click="choose(item)">{{ item.name }}</button>
        </aside>
        <section class="catalog-content">
            <div class="section-head"><div><p class="eyebrow">PRODUCT DETAILS</p><h2>{{ active?.name }}</h2></div><span class="product-count">共 {{ products.length }} 款产品</span></div>
            <div class="detail-grid">
                <button v-for="product in products" :key="product.image" class="detail-card" @click="preview = product">
                    <span><img :src="productImage(product)" :alt="product.title"></span><b>{{ product.title }}</b><i>查看大图 →</i>
                </button>
            </div>
        </section>
    </main>
    <div v-if="preview" class="image-modal" role="dialog" aria-modal="true" :aria-label="preview.title" @click.self="preview = null">
        <button class="modal-close" aria-label="关闭" @click="preview = null">×</button>
        <figure><img :src="productImage(preview)" :alt="preview.title"><figcaption>{{ preview.title }}　<a :href="productImage(preview)" target="_blank" rel="noopener">在新窗口查看原图 →</a></figcaption></figure>
    </div>
</template>
