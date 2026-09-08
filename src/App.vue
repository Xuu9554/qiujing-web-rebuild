<script setup>
    import {ref} from 'vue'
    import SiteHeader from './components/SiteHeader.vue'
    import SiteFooter from './components/SiteFooter.vue'
    import HomeView from './views/HomeView.vue'
    import AboutView from './views/AboutView.vue'
    import ProductsView from './views/ProductsView.vue'
    import ContactView from './views/ContactView.vue'
    import FeedbackView from './views/FeedbackView.vue'
    import {categories} from './data/products'

    const page = ref('home')
    const selected = ref(null)
    const navigate = target => {
        page.value = target;
        selected.value = null;
        window.scrollTo({top: 0, behavior: 'smooth'})
    }
    const select = item => {
        page.value = 'products';
        selected.value = item;
        window.scrollTo({top: 0, behavior: 'smooth'})
    }
    const views = {
        home: HomeView,
        about: AboutView,
        products: ProductsView,
        contact: ContactView,
        feedback: FeedbackView
    }
</script>
<template>
    <SiteHeader :page="page" @navigate="navigate"/>
    <component :is="views[page]" :items="categories" :selected="selected" @navigate="navigate" @select="select"/>
    <SiteFooter/>
</template>

