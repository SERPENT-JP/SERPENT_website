<template>
    <footer class="page-footer"></footer>
</template>

<script>
export default {
    name: "Footer",
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
    margin-top: 14px;
}
li {
    list-style: none;
}
.main-nav {
    display: flex;
    font-size: 1.25rem;
    text-transform: uppercase;
    margin-top: 34px;
    list-style: none;
}
.main-nav li {
    margin-left: 36px;
}
.main-nav a {
    color: #432;
}
.main-nav a:hover {
    color: #0bd;
}
.page-footer {
    height: 30vh;
    display: flex;
    justify-content: space-between;
    background-color: rgb(134, 121, 110);
}
</style>
