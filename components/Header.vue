<template>
    <header class="wrapper">
        <div class="page-header">
            <nuxt-link to="/">
                <img
                    class="logo"
                    src="~/assets/images/SERPENT_FIX.png"
                    alt="SERPENTホーム"
                />
            </nuxt-link>
            <nav class="nav-pc">
                <ul class="main-nav-pc">
                    <li><nuxt-link to="/about">About</nuxt-link></li>
                    <li><nuxt-link to="/member">Member</nuxt-link></li>
                    <li><nuxt-link to="/news">News</nuxt-link></li>
                    <li><nuxt-link to="/blog">Blog</nuxt-link></li>
                    <li><nuxt-link to="/contact">Contact</nuxt-link></li>
                    <li><nuxt-link to="/privacy">Privacy Policy</nuxt-link></li>
                </ul>
            </nav>
            <div class="menu-trigger" id="hamburger" v-on:click="open">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
        <nav class="nav-mobile" id="nav-mobile">
            <ul class="main-nav-mobile">
                <li v-on:click="close">
                    <nuxt-link to="/about">About</nuxt-link>
                </li>
                <li v-on:click="close">
                    <nuxt-link to="/member">Member</nuxt-link>
                </li>
                <li v-on:click="close">
                    <nuxt-link to="/news">News</nuxt-link>
                </li>
                <li v-on:click="close">
                    <nuxt-link to="/blog">Blog</nuxt-link>
                </li>
                <li v-on:click="close">
                    <nuxt-link to="/contact">Contact</nuxt-link>
                </li>
                <li v-on:click="close">
                    <nuxt-link to="/privacy">Privacy Policy</nuxt-link>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
    name: "Header",
    methods: {
        open: function () {
            if (
                document
                    .getElementById("hamburger")
                    .classList.contains("active") == true
            ) {
                document.getElementById("hamburger").classList.remove("active");
                document.getElementById("nav-mobile").style.top = "-105%";
                document.getElementById("nav-mobile").style.transition =
                    "ease 0.5s";
            } else {
                document.getElementById("hamburger").classList.add("active");
                document.getElementById("nav-mobile").style.top = "100px";
                document.getElementById("nav-mobile").style.transition =
                    "ease 0.5s";
            }
        },
        close: function () {
            document.getElementById("hamburger").classList.remove("active");
            document.getElementById("nav-mobile").style.top = "-105%";
            document.getElementById("nav-mobile").style.transition = "ease 0s";
        },
    },
};
</script>

<style scoped>
a {
    text-decoration: none;
}
img {
    max-width: 100%;
}
.logo {
    width: 250px;
    margin: 14px;
}
li {
    list-style: none;
}
.main-nav-pc {
    display: flex;
    font-size: 1.25rem;
    text-transform: uppercase;
    margin-top: 34px;
    list-style: none;
    padding: 0;
    text-align: center;
}
.main-nav-pc li {
    padding: 0 15px;
}
.main-nav-pc a,
.main-nav-mobile a {
    color: #432;
    white-space: nowrap;
}
.main-nav-pc a:hover,
.main-nav-mobile a:hover {
    color: #0bd;
}
.page-header {
    display: flex;
    justify-content: space-between;
    height: 100px;
    z-index: 2;
    position: absolute;
    width: 100%;
    background-color: white;
    top: 0;
    left: 0;
    right: 0;
    padding: 0 13%;
}
.wrapper {
    max-width: 1050px;
}
.nav-pc {
    display: block;
}
.nav-mobile {
    display: none;
    position: absolute;
    z-index: 1;
    height: calc(100vh - 100px);
    width: 100%;
    background-color: rgba(56, 56, 56, 0.9);
    top: -105%;
}
.main-nav-mobile {
    padding: 0;
    text-align: center;
}
.main-nav-mobile li {
    width: 90%;
    margin: 0 5%;
}
.main-nav-mobile li:not(:last-child) {
    border-bottom: 1px white solid;
}
.main-nav-mobile li a {
    color: white;
    display: block;
    height: inherit;
    padding: 30px 0;
    font-size: 1.25rem;
    text-transform: uppercase;
}
.menu-trigger,
.menu-trigger span {
    display: inline-block;
    transition: all 0.4s;
    box-sizing: border-box;
}
.menu-trigger {
    display: none;
    position: relative;
    width: 50px;
    height: 44px;
    margin: 25px;
}
.menu-trigger span {
    position: absolute;
    left: 0;
    width: 100%;
    height: 4px;
    background-color: rgb(56, 56, 56);
    border-radius: 4px;
}
.menu-trigger span:nth-of-type(1) {
    top: 0;
}
.menu-trigger span:nth-of-type(2) {
    top: 20px;
}
.menu-trigger span:nth-of-type(3) {
    bottom: 0;
}
.menu-trigger.active span:nth-of-type(1) {
    -webkit-transform: translateY(20px) rotate(-45deg);
    transform: translateY(20px) rotate(-45deg);
}
.menu-trigger.active span:nth-of-type(2) {
    opacity: 0;
}
.menu-trigger.active span:nth-of-type(3) {
    -webkit-transform: translateY(-20px) rotate(45deg);
    transform: translateY(-20px) rotate(45deg);
}

@media (max-width: 1300px) {
    .page-header {
        padding: 0 5%;
    }
}
@media (max-width: 1050px) {
    .nav-pc {
        display: none;
    }
    .nav-mobile {
        display: block;
    }
    .menu-trigger {
        display: block;
    }
}
</style>
