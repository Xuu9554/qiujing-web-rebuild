<template>
    <section class="page-hero">
        <div class="shell"><p class="eyebrow">CONTACT US</p>
            <h1>联系我们</h1>
            <p>期待与您沟通，为您提供贴心服务。</p></div>
    </section>
    <main class="shell section contact-layout">
        <div><p class="eyebrow">GET IN TOUCH</p>
            <h2>求精（宁波）水暖器材厂</h2>
            <dl>
                <dt>地址</dt>
                <dd><a class="map-address" :href="amapUrl" target="_blank" rel="noopener noreferrer" title="在高德地图中查看">宁波市集士港工业园集发路58号</a></dd>
                <dt>电话</dt>
                <dd>0574-88005026 / 0574-88422426</dd>
                <dt>传真</dt>
                <dd>0574-88423066 / 0574-88192836</dd>
                <dt>邮箱</dt>
                <dd><a href="mailto:qiujing@nbqiujing.com">qiujing@nbqiujing.com</a></dd>
            </dl>
        </div>
        <a class="contact-map-card" :href="amapUrl" target="_blank" rel="noopener noreferrer"><span>QIUJING</span><b>专业水暖<br>品质相伴</b><i>高德地图导航 →</i></a>
    </main>
</template>
<script setup>
const amapUrl = 'https://uri.amap.com/marker?position=121.455228,29.866917&name=%E6%B1%82%E7%B2%BE%EF%BC%88%E5%AE%81%E6%B3%A2%EF%BC%89%E6%B0%B4%E6%9A%96%E5%99%A8%E6%9D%90%E5%8E%82&src=qiujing-web&coordinate=gaode&callnative=1'
</script>

