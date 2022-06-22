<template>
    <!-- leftMenu -->
    <div id="leftMenu">
        <ul class="left_menu">
            <li v-for="menu in menus" :key="menu"><a v-bind:href="menu.link">{{menu.name}}</a></li>
        </ul>
    </div>
    <!-- // leftMenu -->
</template>

<script>
export default {
    name: "leftMenu",
    props: {
        menus: Array,
    },
}
</script>

<style lang="scss">
@import "@/assets/scss/layouts/leftMenu.scss";
</style>