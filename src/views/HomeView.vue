<script setup>
    import {categories} from '../data/products'
    import ProductGrid from '../components/ProductGrid.vue'

    const emit = defineEmits(['navigate', 'select'])
</script>
<template>
    <section class="hero">
        <div class="shell hero-content"><p class="eyebrow">SINCE 2002 · NINGBO</p>
            <h1>匠心制造<br><em>品质水暖</em></h1>
            <p>专注中高档水暖器材、卫浴洁具与水疗设备，为工程与家庭提供可靠选择。</p>
            <button class="primary" @click="emit('navigate','products')">浏览产品系列 <span>→</span></button>
        </div>
    </section>
    <section class="shell intro section">
        <div class="section-head">
            <div><p class="eyebrow">ABOUT QIUJING</p>
                <h2>专注制造二十余年</h2></div>
            <button class="text-link" @click="emit('navigate','about')">了解求精 →</button>
        </div>
        <div class="intro-grid">
            <div class="intro-image"><img src="../assets/image/i_company_bg.jpg" alt="求精工厂">
                <div><b>20+</b><span>年行业深耕</span></div>
            </div>
            <div class="intro-text"><p>求精（宁波）水暖器材厂坐落于宁波，长期专注于水暖器材、卫浴洁具、水疗设备、喷泉喷灌、消防器材及管道配件的研发与制造。</p>
                <p>我们坚持以精良工艺、稳定质量和周到服务，满足不同场景的产品需求。</p>
                <div class="stats"><span><b>100+</b>产品型号</span><span><b>24h</b>响应服务</span><span><b>全国</b>服务网络</span>
                </div>
            </div>
        </div>
    </section>
    <section class="products-section">
        <div class="shell section">
            <div class="section-head">
                <div><p class="eyebrow">PRODUCT RANGE</p>
                    <h2>产品系列</h2></div>
                <button class="text-link" @click="emit('navigate','products')">全部产品 →</button>
            </div>
            <ProductGrid :items="categories.slice(0, 8)" @select="emit('select', $event)"/>
        </div>
    </section>
    <section class="shell contact-banner">
        <div><p class="eyebrow">CONTACT US</p>
            <h2>正在寻找适合的产品方案？</h2>
            <p>欢迎联系求精团队，获取产品咨询与服务支持。</p></div>
        <button class="light-button" @click="emit('navigate','contact')">联系我们</button>
    </section>
</template>
