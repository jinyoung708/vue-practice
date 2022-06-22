<template>
    <!-- header -->
    <header id="header">
        <button type="button" class="menu_btn" @click="toggleMenu()">
            <i class="fa-solid fa-angles-left" v-if="leftShow == true"></i>
            <i class="fa-solid fa-bars-staggered" v-else></i>
        </button>
        <h1 class="logo">Publishing Practice</h1>
        <ul class="link_list clearfix">
            <li v-for="menu in menus" :key="menu"><a v-bind:href="menu.link">{{menu.name}}</a></li>
        </ul>
    </header>
    <!-- // header -->
</template>

<script>
export default {
    name: "Header",
    props: {
        leftShow: Boolean,
        menus: Array,
    },
    methods: {
        toggleMenu(){
            this.$emit('toggleMenu', this.leftShow);
        }
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/layouts/header.scss";
</style>