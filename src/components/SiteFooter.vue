<script setup>
    const currentYear = new Date().getFullYear()
</script>

<template>
    <footer class="footer">
        <div class="shell footer-grid">
            <div>
                <div class="footer-brand">求精 <span>QIUJING</span></div>
                <p>为客户提供可靠的水暖、卫浴与管道配件产品。</p></div>
            <div><b>联系我们</b>
                <p>宁波市集士港工业园集发路58号<br>0574-88005026 · qiujing@nbqiujing.com</p></div>
            <div><b>产品服务</b>
                <p>水暖器材　卫浴洁具<br>水疗设备　管道配件</p></div>
        </div>
        <div class="copyright">
            © {{ currentYear }} 求精（宁波）水暖器材厂 ·
            <a href="https://beian.miit.gov.cn/" target="_blank" rel="noopener noreferrer">浙ICP备2026073096号</a>
        </div>
    </footer>
</template>
