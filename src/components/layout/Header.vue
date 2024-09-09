<script setup lang="ts">
import { ref } from 'vue';
const menuItems = ref([
    {
        label: "Indie Game",
        url: "/"
    },
    {
        label: "Entry Game",
        url: "/"
    },
    {
        label: "Community",
        url: "/"
    }
])
</script>

<template>
  <header class="header">
    <div class="container">
        <div class="header__content">
            <a href="/" class="logo">
                <img src="/sOCVfKv.png"  alt="logo"/>
            </a>
            <nav class="nav">
            <ul class="menu">
                <li v-for="(menu, index) in menuItems" :key="index">
                    <a :href="menu.url">{{menu.label}}</a>
                </li>
            </ul>
            </nav>
        </div>
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
    background-color: #02cc9a;
    padding: 10px 0;
    &__content {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .logo {
        width: 80px;
    }
    .nav {
        .menu {
            display: none;
        }
        @media (min-width: 768px) {
            .menu {
                display: flex;
            }
        }
    }
}
.nav {
    .menu {
        padding: 0;
        margin: 0;
        list-style: none;
        display: flex;
        column-gap: 15px;
    }
    li {
        a {
            display: inline-block;
            border: 1px solid white;
            border-radius: 4px;
            color: white;
            text-decoration: none;
            padding: 2px 10px;
            font-size: 14px;
        }
    }
}
</style>
