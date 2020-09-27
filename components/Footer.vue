<template>
    <footer class="page-footer">
        <div class="footer-box">
            <div class="footer-meta-box">
                <h2 class="footer-title">SERPENT</h2>
                <p class="footer-sub-title">lunched by students</p>
                <a href="https://twitter.com/SERPENT_4">
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="24"
                        height="24"
                        viewBox="0 0 24 24"
                        class="footer-svg"
                    >
                        <path
                            d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
                        />
                    </svg>
                </a>
                <p class="copylight">©2020 SERPENT-JP.com</p>
            </div>
            <div class="site-map">
                <div class="site-map-left">
                    <h4>HomePage</h4>
                    <a href="/">Top</a>
                    <br />
                    <a href="/about">About</a>
                    <br />
                    <a href="/member">Member</a>
                    <br />
                    <a href="/news">News</a>
                    <br />
                    <a href="/blog">Blog</a>
                    <br />
                    <a href="/contact">Contact</a>
                    <br />
                    <a href="/privacy">PrivacyPolicy</a>
                </div>
                <div class="site-map-right">
                    <h4>Blog</h4>
                </div>
            </div>
        </div>
    </footer>
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
    background-color: #333;
    padding: 30px 20%;
}
.footer-box {
    position: relative;
    width: 100%;
}
.footer-meta-box {
    width: min-content;
    height: min-content;
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    margin: auto;
}
.footer-title {
    font-family: "Domine", serif;
    font-size: 40px;
    color: #ddd;
}
.footer-sub-title {
    font-family: "Domine", serif;
    white-space: nowrap;
    color: #ddd;
}
.footer-svg {
    fill: #ddd;
}
.copylight {
    font-size: 14px;
    margin-top: 80px;
    white-space: nowrap;
    color: #ddd;
}
.site-map {
    width: min-content;
    height: min-content;
    position: absolute;
    right: 0;
    top: 0;
    bottom: 0;
    margin: auto;
    display: flex;
}
.site-map-left {
    font-family: "Domine", serif;
    width: 200px;
}
.site-map-left h4 {
    color: #ddd;
    font-size: 25px;
}
.site-map-left > a {
    width: 100%;
    color: #999;
    font-size: 17px;
    padding-left: 5px;
}
.site-map-right {
    color: #ddd;
    font-family: "Domine", serif;
    width: 200px;
}
@media (max-width: 1100px) {
    .page-footer {
        padding: 30px;
    }
}
@media (max-width: 700px) {
    .page-footer {
        padding: 10px;
    }
    .footer-meta-box {
        position: initial;
    }
    .site-map {
        position: initial;
    }
    .page-footer {
        height: auto;
    }
    .site-map-left,
    .site-map-right {
        width: 170px;
    }
}
</style>
