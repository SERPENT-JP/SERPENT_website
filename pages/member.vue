<template>
    <div class="member-outer">
        <h1 class="member-title">メンバーリスト</h1>
        <div style="list-style:none">
            <li>
                <ul v-for="item in list" :key="item.id">
                    <div class="author-box">
                        <div class="icon-outer">
                            <img :src="item.icon" class="icon" />
                        </div>
                        <div class="author-box-detail">
                            <div class="name-box">
                                <span class="name">{{ item.name }}</span>
                                <span
                                    v-if="item.role == 'オーナー'"
                                    class="role-owner role"
                                >{{ item.role }}</span>
                                <span v-if="item.role == '１期生'" class="role-1 role">{{ item.role }}</span>
                                <span v-if="item.role == '２期生'" class="role-2 role">{{ item.role }}</span>
                                <span v-if="item.role == '３期生'" class="role-3 role">{{ item.role }}</span>
                                <span v-if="item.role == '４期生'" class="role-4 role">{{ item.role }}</span>
                            </div>
                            <hr />
                            <p>{{ item.description }}</p>
                            <div class="meta-box">
                                <div class="meta-box-inner">
                                    <a
                                        class="twitter-button btn"
                                        v-bind:href="'https://twitter.com/' + item.TwitterID"
                                        v-if="item.TwitterID"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            width="24"
                                            height="24"
                                            viewBox="0 0 24 24"
                                            class="twitter-svg"
                                        >
                                            <path
                                                d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
                                            />
                                        </svg>
                                        <br />
                                        Follow @{{ item.TwitterID }}
                                    </a>
                                    <a
                                        class="github-button btn"
                                        v-bind:href="'https://github.com/' + item.GitID"
                                        v-if="item.GitID"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            width="24"
                                            height="24"
                                            viewBox="0 0 24 24"
                                            class="git-svg"
                                        >
                                            <path
                                                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                                            />
                                        </svg>
                                        <br />
                                        Follow @{{ item.GitID }}
                                    </a>
                                    <a
                                        class="mailadress btn"
                                        v-bind:href="'mailto:' + item.MailAdress"
                                        v-if="item.MailAdress"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            xmlns:xlink="http://www.w3.org/1999/xlink"
                                            version="1.1"
                                            id="_x32_"
                                            x="0px"
                                            y="0px"
                                            viewBox="0 0 512 512"
                                            class="mail-svg"
                                            xml:space="preserve"
                                        >
                                            <g>
                                                <path
                                                    class="st0"
                                                    d="M510.678,112.275c-2.308-11.626-7.463-22.265-14.662-31.054c-1.518-1.915-3.104-3.63-4.823-5.345   c-12.755-12.818-30.657-20.814-50.214-20.814H71.021c-19.557,0-37.395,7.996-50.21,20.814c-1.715,1.715-3.301,3.43-4.823,5.345   C8.785,90.009,3.63,100.649,1.386,112.275C0.464,116.762,0,121.399,0,126.087V385.92c0,9.968,2.114,19.55,5.884,28.203   c3.497,8.26,8.653,15.734,14.926,22.001c1.59,1.586,3.169,3.044,4.892,4.494c12.286,10.175,28.145,16.32,45.319,16.32h369.958   c17.18,0,33.108-6.145,45.323-16.384c1.718-1.386,3.305-2.844,4.891-4.43c6.27-6.267,11.425-13.741,14.994-22.001v-0.064   c3.769-8.653,5.812-18.171,5.812-28.138V126.087C512,121.399,511.543,116.762,510.678,112.275z M46.509,101.571   c6.345-6.338,14.866-10.175,24.512-10.175h369.958c9.646,0,18.242,3.837,24.512,10.175c1.122,1.129,2.179,2.387,3.112,3.637   L274.696,274.203c-5.348,4.687-11.954,7.002-18.696,7.002c-6.674,0-13.276-2.315-18.695-7.002L43.472,105.136   C44.33,103.886,45.387,102.7,46.509,101.571z M36.334,385.92V142.735L176.658,265.15L36.405,387.435   C36.334,386.971,36.334,386.449,36.334,385.92z M440.979,420.597H71.021c-6.281,0-12.158-1.651-17.174-4.552l147.978-128.959   l13.815,12.018c11.561,10.046,26.028,15.134,40.36,15.134c14.406,0,28.872-5.088,40.432-15.134l13.808-12.018l147.92,128.959   C453.137,418.946,447.26,420.597,440.979,420.597z M475.666,385.92c0,0.529,0,1.051-0.068,1.515L335.346,265.221L475.666,142.8   V385.92z"
                                                />
                                            </g>
                                        </svg>
                                        <br />
                                        {{ item.MailAdress }}
                                    </a>
                                </div>
                                <a
                                    class="to-blog"
                                    v-bind:href="'https://blog.serpent-jp.com/author/' + item.name"
                                >{{item.name}} の書いたブログ記事を見る</a>
                            </div>
                        </div>
                    </div>
                    <hr />
                </ul>
            </li>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data() {
        return {
            list: [],
        };
    },
    mounted() {
        axios
            .get("http://serpent.pythonanywhere.com/api/author/")
            .then((response) => (this.list = response.data));
    },
};
</script>

<style>
.member-outer {
    padding: 0 10%;
}
.member-title {
    text-align: center;
    margin: 50px 0;
}
.author-box {
    display: flex;
}
.author-box-detail {
    padding-left: 20px;
    width: 100%;
    margin-right: 5%;
}
.icon-outer {
    min-width: 300px;
    min-height: 300px;
}
.icon {
    border-radius: 100%;
    width: 100%;
    height: 100%;
}
.role {
    position: absolute;
    padding: 7px;
    border-radius: 5px;
    font-size: 15px;
}
.role-owner {
    background-color: rgb(70, 221, 95);
}
.role-1 {
    background-color: rgb(221, 191, 70);
}
.role-2 {
    background-color: rgb(221, 110, 70);
}
.role-3 {
    background-color: rgb(221, 70, 173);
}
.role-4 {
    background-color: rgb(149, 132, 201);
}
.name-box {
    position: relative;
}
.meta-box {
    text-align: center;
}
.meta-box-inner {
    width: 100%;
    display: flex;
}
.btn {
  margin: 0 50px;
}
.name {
    font-weight: bold;
    font-size: 25px;
    padding: 0 15px;
}
.twitter-button {
    color: white;
    background-color: rgb(29, 161, 242);
    font-weight: bold;
    font-size: 13px;
    line-height: 26px;
    padding: 5px;
    border-radius: 5px;
}
.twitter-button:hover {
    text-decoration: none;
    color: white;
    background-color: rgb(22, 125, 189);
}
.twitter-svg {
    width: 20px;
    fill: white;
}
.github-button {
    color: white;
    background-color: rgb(75, 75, 75);
    font-weight: bold;
    font-size: 13px;
    line-height: 26px;
    padding: 5px;
    border-radius: 5px;
}
.github-button:hover {
    text-decoration: none;
    color: white;
    background-color: rgb(36, 36, 36);
}
.git-svg {
    fill: white;
    width: 20px;
}
.mailadress {
    color: white;
    background-color: rgb(238, 74, 74);
    font-weight: bold;
    font-size: 13px;
    line-height: 26px;
    padding: 5px;
    border-radius: 5px;
}
.mailadress:hover {
    text-decoration: none;
    color: white;
    background-color: rgb(189, 22, 22);
}
.mail-svg {
    width: 20px;
    fill: white;
}
.to-blog {
    margin-top: 40px;
    display: inline-block;
    background-color: #26a69b;
    color: #fff;
    font-size: 1em;
    line-height: 1;
    text-decoration: none;
    letter-spacing: 0.05em;
    padding: 1em;
    border-radius: 3px;
    cursor: pointer;
    box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 1px 5px 0 rgba(0, 0, 0, 0.12),
        0 3px 1px -2px rgba(51, 51, 51, 0.2);
    -webkit-tap-highlight-color: transparent;
    transition: 0.3s ease-out;
    font-weight: bold;
}

.to-blog:hover {
    box-shadow: 0 3px 3px 0 rgba(0, 0, 0, 0.14), 0 1px 7px 0 rgba(0, 0, 0, 0.12),
        0 3px 1px -1px rgba(0, 0, 0, 0.2);
    text-decoration: none;
    color: black;
}
</style>
