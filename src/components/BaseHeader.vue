<template>
    <div>
        <h1>
            <router-link to="/">
                <img src="../assets/img/logo.png" alt="logo/nom(Cathie Flammant)" @click="scrollToTop">
                | Développeuse web junior | Portfolio
            </router-link> 
        </h1>

        <nav>
            <ul>
                <li><router-link :to="{ path: '/', hash: '#presentation' }" :class="{ active: isActive('#presentation') }">Qui suis-je ?</router-link></li>
                <li><router-link :to="{ path: '/', hash: '#projects' }" :class="{ active: isActive('#projects') }">Projets</router-link></li>
                <li><router-link :to="{ path: '/', hash: '#contact' }" :class="{ active: isActive('#contact') }">Contact</router-link></li>
            </ul>
        </nav>
    </div>
</template>

<script setup>
    import { useRoute } from 'vue-router';

    const route = useRoute();

    const isActive = (hash) => {
        return route.hash === hash;
    };

    const scrollToTop = () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    };
</script>

<style scoped>
    div {
        background-color: #0D141F;
        display: flex;
        flex-direction: row;
        align-items: center;
        align-content: space-between;
        position: fixed;
        top: 0;
        width: 100%;
        padding: 0;
        margin: 0;
    }

    h1{
        width: 50%;
        font-size: small;
    }

    img{
        width: 50%;
    }

    a {
        text-decoration: none;
        color: #FFD60A;
        font-size: small;
    }

    nav{
        display: flex;
        justify-content: flex-end;
        width: 100%;
    }

    ul {
        list-style-type: none;
        display: flex;
        gap: 40px;
        margin-right: 25px;
    }

    li a:hover{
        text-decoration: underline;
        color: #FFE7B3;
    }

    .active {
        text-decoration: underline;
        color: #FFE7B3;
    }

    @media screen and (max-width: 768px) {
        div {
            flex-direction: column;
            align-items: center;
        }

        h1, nav {
            width: 100%;
            text-align: center;
            margin: 5px 0;
            font-size: 60%;
        }

        nav{
            justify-content: center;
        }
    }  
</style>