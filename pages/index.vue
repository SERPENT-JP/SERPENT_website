<template>
    <div class="index-outer wrapper">
        <div class="index-left">
            <img
                class="index-img"
                src="~/assets/images/index-img.svg"
                alt="SERPENTイメージ"
            />
        </div>
        <div class="index-right">
            <div class="index-message">
                <h2>夢を育てる場</h2>
                <h1>SERPENT</h1>
                <p>lunched by students</p>
            </div>
            <a class="to-about" href="/about/">
                to About
                <img
                    class="to-about-img"
                    src="~/assets/images/next.svg"
                    alt="toAbout"
                />
            </a>
        </div>
    </div>
</template>

<script>
</script>

<style>
.index-outer {
    height: calc(100vh - 100px);
    display: flex;
}
.index-left {
    width: 50%;
    background: linear-gradient(
        150.46deg,
        rgba(242, 182, 182, 0.8) 0%,
        rgba(182, 228, 242, 0.8) 100%
    );
    position: relative;
}
.index-right {
    width: 50%;
    text-align: center;
}
.wrapper {
    margin: 0 auto;
}
.index-img {
    width: 70%;
    margin: 0 15% 5% 15%;
    position: absolute;
    bottom: 0;
}
.index-message {
    margin: 20vh auto 100px auto;
    text-align: center;
}
.index-message > h2 {
    font-size: 50px;
}
.index-message > h1 {
    font-size: 100px;
    font-family: "Domine", serif;
}
.index-message > p {
    font-size: 25px;
}
.to-about {
    background-color: #aadde4;
    border-radius: 200px;
    text-decoration: none;
    color: black;
    font-size: 40px;
    padding: 10px 70px 10px 30px;
    height: 50px;
    position: relative;
    font-family: "David Libre", serif;
    font-family: "Domine", serif;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
}
.to-about:hover {
    background-color: rgb(125, 215, 231);
    color: black;
    text-decoration: none;
    box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 5px 5px 5px rgba(0, 0, 0, 0.22);
}
.to-about-img {
    position: absolute;
    right: 0;
    top: 0;
    width: 40px;
    margin: 15px;
}
@media (max-width: 1000px) {
    .index-left {
        display: none;
    }
    .index-right {
        width: 100%;
        background: linear-gradient(
            150.46deg,
            rgba(242, 182, 182, 0.8) 0%,
            rgba(182, 228, 242, 0.8) 100%
        );
    }
    .index-message {
        margin-top: 100px;
    }
    .index-message > h1 {
        font-size: 50px;
        font-family: "Domine", serif;
    }
    .index-message > h2 {
        font-size: 30px;
    }
}
</style>
