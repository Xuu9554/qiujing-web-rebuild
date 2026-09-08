<script setup>import {ref} from 'vue';

const sent = ref(false);
const submit = () => {
    sent.value = true
}</script>
<template>
    <section class="page-hero">
        <div class="shell"><p class="eyebrow">MESSAGE</p>
            <h1>在线留言</h1>
            <p>请留下您的需求，我们会尽快与您联系。</p></div>
    </section>
    <main class="shell section form-wrap">
        <form @submit.prevent="submit"><label>您的称呼<input required placeholder="请输入姓名"></label><label>联系电话<input required
                                                                                                                placeholder="请输入联系电话"></label><label>电子邮箱<input
                type="email" placeholder="请输入电子邮箱"></label><label>留言内容<textarea required
                                                                                placeholder="请描述您的产品需求或合作意向"></textarea></label>
            <button class="primary" type="submit">提交留言 <span>→</span></button>
            <p v-if="sent" class="form-success">留言已保存到前端演示状态，后端接入后可在此提交至接口。</p></form>
    </main>
</template>
