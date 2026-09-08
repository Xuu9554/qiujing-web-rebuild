<script setup>
    defineProps({page: String})
    const emit = defineEmits(['navigate'])
    const nav = [['home', '首页'], ['about', '关于我们'], ['products', '产品展示'], ['contact', '联系我们'], ['feedback', '在线留言']]
</script>

<template>
    <header class="site-header">
        <div class="topline">
            <div class="shell topline-inner"><span>专注水暖器材 · 卫浴洁具 · 水疗设备</span></div>
        </div>
        <div class="shell brand-row">
            <button class="brand" @click="emit('navigate', 'home')"><span
                    class="brand-mark">QJ</span><span><b>求精</b><small>QIUJING SANITARY WARE</small></span></button>
            <div class="brand-copy"><strong>求精（宁波）水暖器材厂</strong><span>品质源于专注，服务始于用心</span></div>
            <a class="phone" href="tel:4006005026"><span>咨询热线</span><b>400-600-5026</b></a>
        </div>
        <nav class="nav">
            <div class="shell nav-inner">
                <button v-for="item in nav" :key="item[0]" :class="{active: page === item[0]}"
                        @click="emit('navigate', item[0])">{{ item[1] }}
                </button>
            </div>
        </nav>
    </header>
</template>

