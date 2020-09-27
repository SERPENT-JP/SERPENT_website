<template>
    <div>
        <div class="about-outer">
            <div class="top-left">
                <div class="top-message">
                    <h1 calss="top-title">About</h1>
                </div>
                <div class="left-message">
                    <h2 class="left-passage">
                        中高生の夢を大切に
                        <br />高め合い、実現させる
                    </h2>
                </div>
            </div>
            <div class="top-right">
                <img
                    class="about-top-img"
                    src="~/assets/images/about-top-img.svg"
                    alt="Aboutトップイメージ"
                />
            </div>
        </div>
        <div class="content-card-gray">
            <img src="~/assets/images/mokumoku.png" alt="もくもく会" />
            <div class="discription-box-gray">
                <h2>もくもく会</h2>
                <hr />
                <p>
                    SERPENTでは不定期で「もくもく会」という作業通話活動をしています。メンバー内でお互いの中を深め合ったり、同じ志の仲間同士と知識を共有したり、わからないところは教え合うなどしてそれぞれのモチベーションのために開催しています。
                </p>
            </div>
        </div>
        <div class="content-card-white">
            <div class="discription-box-white">
                <h2>ブログ活動</h2>
                <hr />
                <p>
                    SERPENTでは独自の技術系ブログを制作、投稿、運営をしています。サーペントメンバー内のウェブ担当者がNuxtやDjangoを使って実装しました。このブログ活動を通して、ポートフォリオのような形で活動を残し、情報を発信する立場となればいいなと思っています。
                </p>
            </div>
            <img class src="~/assets/images/mokumoku.png" alt="ブログ" />
        </div>
        <div class="content-card-gray">
            <img src="~/assets/images/SERPENT-Git.png" alt="Git" />
            <div class="discription-box-gray">
                <h2>共同開発</h2>
                <hr />
                <p>
                    さらにSERPENTでは、同じ志を持った仲間同士で手を組み、実戦形式でGitOrganizationを使用してより本番に近い形で開発ができるような練習も兼ねて、共同開発を進めています。このホームページやブログも、実際にサーペントが共同開発をして作ったものです。
                </p>
            </div>
        </div>
        <div class="content-card-white">
            <div class="discription-box-white">
                <h2>Discord</h2>
                <hr />
                <p>
                    SERPENTは主にDiscord上で活動をしています。Discord上で日常の活動報告や雑談、技術・情報共有にプロジェクトの発案・打ち合わせなど、様々な会話が進められ、メンバー内で自主的に活動が進められています。
                </p>
            </div>
            <img class src="~/assets/images/Discord.png" alt="Discord" />
        </div>
    </div>
</template>

<script>
</script>

<style>
.about-outer {
    display: flex;
    text-align: center;
}
.about-top-img {
    padding: 5% 20% 5% 0;
    width: 80%;
}
.left-message {
    position: absolute;
    width: 450px;
    padding: 0 40px;
    bottom: 50px;
    left: 0;
    right: 0;
    margin: auto;
    border-left: gray 2px solid;
}
.top-message {
    position: absolute;
    width: 60%;
    margin: 15vh auto 0 auto;
    left: 0;
    right: 0;
}
.top-message > h1::before {
    position: absolute;
    content: " ";
    display: block;
    border-top: solid 2px gray;
    top: -20px;
    width: 150px;
}
.top-message > h1 {
    font-size: 80px;
    margin: auto;
    text-align: center;
    font-family: "Domine", serif;
    position: absolute;
    left: 0;
    right: 0;
    width: min-content;
}
.top-left {
    width: 50%;
    position: relative;
}
.top-right {
    width: 50%;
}
.content-card-gray {
    width: 90%;
    margin: 20px 5%;
    height: 60vh;
    background-color: rgb(153, 153, 153);
    position: relative;
}
.content-card-gray > img {
    margin: auto 0 auto 3%;
    width: 47%;
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
}
.discription-box-gray {
    right: 0;
    margin: auto 3% auto 0;
    width: 47%;
    height: 80%;
    position: absolute;
    top: 0;
    bottom: 0;
    text-align: center;
}
.discription-box-gray > h2 {
    font-weight: bold;
    font-size: 45px;
    font-family: "M PLUS Rounded 1c", sans-serif;
    color: white;
}
.discription-box-gray > p {
    padding: 30px;
    font-family: "M PLUS Rounded 1c", sans-serif;
    color: white;
    font-weight: bold;
    font-size: 25px;
}
.content-card-white {
    width: 90%;
    margin: 20px 5%;
    height: 60vh;
    position: relative;
}
.content-card-white > img {
    margin: auto 3% auto 0;
    width: 47%;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
}
.discription-box-white {
    margin: auto 0 auto 3%;
    width: 47%;
    height: 80%;
    position: absolute;
    top: 0;
    bottom: 0;
    text-align: center;
}
.discription-box-white > h2 {
    font-weight: bold;
    font-size: 45px;
    font-family: "M PLUS Rounded 1c", sans-serif;
    color: gray;
}
.discription-box-white > p {
    padding: 30px 50px;
    font-family: "M PLUS Rounded 1c", sans-serif;
    color: gray;
    font-weight: bold;
    font-size: 25px;
}
@media (max-width: 1200px) {
    .discription-box-white > p,
    .discription-box-gray > p {
        font-size: 20px;
    }
    .discription-box-white > h2,
    .discription-box-gray > h2 {
        font-size: 30px;
    }
}
@media (max-width: 1000px) {
    .about-outer {
        height: 100px;
    }
    .top-right {
        display: none;
    }
    .top-left {
        width: 100%;
    }
    .top-message {
        margin: 0;
        width: 100%;
    }
    .top-message > h1::before {
        position: relative;
        border: none;
        display: inline;
    }
    .top-message > h1 {
        font-size: 80px;
        margin: auto;
        text-align: center;
        font-family: "Domine", serif;
        position: relative;
        width: 100%;
    }
    .left-passage {
        display: none;
    }
    .content-card-gray,
    .content-card-white {
        height: 450px;
        margin: 20px 10px;
        width: calc(100% - 20px);
    }
    .content-card-gray > img,
    .content-card-white > img {
        width: 100%;
        margin: 0;
        padding: 5px;
    }
    .discription-box-gray > p,
    .discription-box-white > p {
        padding: 10px;
        font-size: 15px;
    }
    .discription-box-gray,
    .discription-box-white {
        width: 100%;
        height: min-content;
        margin: 210px 0 0 0;
    }
}
</style>
