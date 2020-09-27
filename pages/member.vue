<template>
    <div class="member-outer">
        <h1 class="member-title">Member List</h1>
        <div style="list-style: none;">
            <li>
                <ul
                    v-for="(item, index) in list.slice(
                        perPage * (currentPage - 1),
                        perPage * currentPage
                    )"
                    :key="index"
                >
                    <div class="author-box">
                        <div class="icon-outer-pc">
                            <img :src="item.icon" class="icon" />
                        </div>
                        <div class="author-box-detail">
                            <div class="name-box">
                                <div class="icon-outer-mobile">
                                    <img :src="item.icon" class="icon" />
                                </div>
                                <span class="name">{{ item.name }}</span>
                                <span
                                    v-if="item.role == 'オーナー'"
                                    class="role-owner role"
                                    >{{ item.role }}</span
                                >
                                <span
                                    v-if="item.role == '１期生'"
                                    class="role-1 role"
                                    >{{ item.role }}</span
                                >
                                <span
                                    v-if="item.role == '２期生'"
                                    class="role-2 role"
                                    >{{ item.role }}</span
                                >
                                <span
                                    v-if="item.role == '３期生'"
                                    class="role-3 role"
                                    >{{ item.role }}</span
                                >
                                <span
                                    v-if="item.role == '４期生'"
                                    class="role-4 role"
                                    >{{ item.role }}</span
                                >
                            </div>
                            <hr class="hr" />
                            <p>{{ item.description }}</p>
                            <div class="meta-box">
                                <div class="meta-box-inner">
                                    <a
                                        class="homepage-button btn"
                                        v-bind:href="item.HomePage"
                                        v-if="item.HomePage"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            width="24"
                                            height="24"
                                            viewBox="0 0 24 24"
                                            class="btn-svg"
                                        >
                                            <path
                                                d="M20 7.093v-5.093h-3v2.093l3 3zm4 5.907l-12-12-12 12h3v10h18v-10h3zm-5 8h-14v-10.26l7-6.912 7 6.99v10.182zm-5-1h-4v-6h4v6z"
                                            />
                                        </svg>
                                        Homepage
                                    </a>
                                    <a
                                        class="twitter-button btn"
                                        v-bind:href="
                                            'https://twitter.com/' +
                                            item.TwitterID
                                        "
                                        v-if="item.TwitterID"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            width="24"
                                            height="24"
                                            viewBox="0 0 24 24"
                                            class="btn-svg"
                                        >
                                            <path
                                                d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"
                                            />
                                        </svg>
                                        @{{ item.TwitterID }}
                                    </a>
                                    <a
                                        class="instagram-button btn"
                                        v-bind:href="
                                            'https://instagram.com/' +
                                            item.InstagramID
                                        "
                                        v-if="item.InstagramID"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            width="24"
                                            height="24"
                                            viewBox="0 0 24 24"
                                            class="btn-svg"
                                        >
                                            <path
                                                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"
                                            />
                                        </svg>
                                        {{ item.InstagramID }}
                                    </a>
                                    <a
                                        class="github-button btn"
                                        v-bind:href="
                                            'https://github.com/' + item.GitID
                                        "
                                        v-if="item.GitID"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            width="24"
                                            height="24"
                                            viewBox="0 0 24 24"
                                            class="btn-svg"
                                        >
                                            <path
                                                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                                            />
                                        </svg>
                                        {{ item.GitID }}
                                    </a>
                                    <a
                                        class="qitta-button btn"
                                        v-bind:href="
                                            'https://qiita.com/' + item.QittaID
                                        "
                                        v-if="item.QittaID"
                                    >
                                        <svg
                                            viewBox="0 0 410.09 356.15"
                                            xmlns="http://www.w3.org/2000/svg"
                                            class="btn-svg"
                                        >
                                            <path
                                                d="M358.15 293.75c-10.23 2.4-19.4-11.91-25.19-19.28-6-7.63-5-15.34-1.68-24.46 7.08-19.47 9.84-39.89 7.34-66.57-4.45-47.25-24.09-88.85-52.95-119.32l-2.16-53.53c-.68-8.45-9.62-13.28-16.68-9l-37.52 22.7a154.16 154.16 0 00-77.25-12.16c-31.67 3.2-60.38 15.94-84.12 35.43L28 37.86c-7.7-1.87-15 5.64-13.1 13.54l11.57 45.45C6.62 131.3-3.22 173.35.94 217.58c9.78 104 90.56 145.69 183.81 136.26 46.05-4.65 84.09-14.48 112.09-44.34 7.21 16.17 20.92 25.9 36.38 36.2 26.74 17.83 58.22 12.38 71.59-12.88 18.74-35.4-16.13-46.23-46.66-39.07zM298.68 138l-22.49-4.89c.5 2.87.92 4.4 1.2 7.34 5.77 61.37-42.27 83.54-103.51 89.73s-112.49-5.94-118.26-67.3c-.28-2.93-.4-4.48-.45-7.37l-20.76 9.71-1.07-5.4 21.8-8.91a85.08 85.08 0 01.72-9.88L32 142.93l-.23-4.38 24.49-2a83.1 83.1 0 011.86-8.48l-28.07-3 .31-5.6 28.5 4.31c11.6-44 49.43-78.41 97.19-83.24s90.11 20 109.65 61l29.14-10.09.86 5.55-27.39 8.74q2 4.5 3.6 9.21l24.87-3 .34 4.36-24.24 3a86.74 86.74 0 012.73 9.36L299.2 133z"
                                                fill="#fff"
                                            />
                                        </svg>
                                        {{ item.QittaID }}
                                    </a>
                                    <a
                                        class="note-button btn"
                                        v-bind:href="
                                            'https://note.com/' + item.NoteID
                                        "
                                        v-if="item.NoteID"
                                    >
                                        <svg
                                            viewBox="100 50 200 280"
                                            xmlns="http://www.w3.org/2000/svg"
                                            xmlns:xlink="http://www.w3.org/1999/xlink"
                                            class="btn-svg"
                                        >
                                            <g
                                                id="white/logo_symbol"
                                                stroke="none"
                                                stroke-width="1"
                                                fill="none"
                                                fill-rule="evenodd"
                                            >
                                                <path
                                                    d="M180.388501,169.6969 L180.388501,155.318324 C180.388501,152.698052 180.524171,151.824229 180.927578,150.479979 C182.005733,146.784785 185.646008,144.030448 189.958629,144.030448 C194.27125,144.030448 197.910324,146.851818 198.988479,150.479979 C199.393087,151.824229 199.528757,152.698052 199.528757,155.318324 L199.528757,177.490682 C199.528757,178.834933 199.528757,180.177986 199.258618,181.388171 C198.517837,184.747003 195.485075,187.771866 192.114939,188.510426 C190.902315,188.778558 189.554021,188.778558 188.205726,188.778558 L165.966674,188.778558 C163.33852,188.778558 162.462069,188.644492 161.113775,188.241097 C157.474701,187.166175 154.644843,183.538015 154.644843,179.238327 C154.644843,174.937443 157.474701,171.309283 161.113775,170.234361 C162.462069,169.830966 163.33852,169.6969 165.966674,169.6969 L180.388501,169.6969 Z M259.642514,270.215259 L140.357486,270.215259 L140.357486,165.464245 C140.357486,164.119995 140.829329,162.97804 141.773015,162.037184 L172.705744,131.196024 C173.64943,130.256366 174.79482,129.785938 176.143114,129.785938 L259.642514,129.785938 L259.642514,270.215259 Z M273.18909,106.134066 C272.582778,106.067033 271.773561,106 270.223563,106 L172.974683,106 C171.897728,106 170.819573,106.067033 170.077591,106.134066 C165.6293,106.537461 161.652852,108.620272 158.485621,111.778004 L122.295384,147.859707 C119.129354,151.018637 117.039078,154.981962 116.63567,159.416912 C116.567235,160.155472 116.5,161.230394 116.5,162.305316 L116.5,280.763379 C116.5,282.308729 116.567235,283.115519 116.63567,283.720012 C117.173547,288.759457 121.756307,293.327276 126.81091,293.864737 C127.418423,293.932967 128.226439,294 129.776437,294 L270.223563,294 C271.773561,294 272.582778,293.932967 273.18909,293.864737 C278.243693,293.327276 282.826453,288.759457 283.365531,283.720012 C283.431565,283.115519 283.5,282.308729 283.5,280.763379 L283.5,119.236621 C283.5,117.691271 283.431565,116.884481 283.365531,116.279988 C282.826453,111.240543 278.243693,106.671527 273.18909,106.134066 Z"
                                                    id="Shape"
                                                    fill="#FFFFFF"
                                                />
                                            </g>
                                        </svg>
                                        {{ item.NoteID }}
                                    </a>
                                    <a
                                        class="hatena-button btn"
                                        v-bind:href="item.HatenaID"
                                        v-if="item.HatenaID"
                                    >
                                        <svg
                                            xmlns="http://www.w3.org/2000/svg"
                                            preserveAspectRatio="none"
                                            viewBox="0 0 100 100"
                                            class="btn-svg"
                                        >
                                            <path
                                                d="M50.1 100.2C22.5 100.2 0 77.7 0 50.1S22.5 0 50.1 0s50.1 22.5 50.1 50.1c-.1 27.6-22.5 50.1-50.1 50.1zm0-93.8C26 6.4 6.4 26 6.4 50.1S26 93.8 50.1 93.8s43.7-19.6 43.7-43.7S74.2 6.4 50.1 6.4z"
                                            />
                                            <path
                                                d="M55.9 25.3c-2.4-5-3.9-9.8-4.7-12.6v35.5c1.2.5 2.1 1.6 2.1 3 0 1.8-1.5 3.3-3.3 3.3-1.8 0-3.3-1.5-3.3-3.3 0-1.5 1-2.7 2.3-3.1V12.7c-.8 2.8-2.2 7.6-4.7 12.6-3.8 7.8-8.6 14.6-8.6 14.6l3.1 41.8s2.9 3.2 11.3 3.2 11.3-3.2 11.3-3.2l3.1-41.8s-4.8-6.8-8.6-14.6z"
                                            />
                                        </svg>
                                        {{ item.HatenaID }}
                                    </a>
                                    <a
                                        class="mailadress btn"
                                        v-bind:href="
                                            'mailto:' + item.MailAdress
                                        "
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
                                            class="btn-svg"
                                            xml:space="preserve"
                                        >
                                            <g>
                                                <path
                                                    class="st0"
                                                    d="M510.678,112.275c-2.308-11.626-7.463-22.265-14.662-31.054c-1.518-1.915-3.104-3.63-4.823-5.345   c-12.755-12.818-30.657-20.814-50.214-20.814H71.021c-19.557,0-37.395,7.996-50.21,20.814c-1.715,1.715-3.301,3.43-4.823,5.345   C8.785,90.009,3.63,100.649,1.386,112.275C0.464,116.762,0,121.399,0,126.087V385.92c0,9.968,2.114,19.55,5.884,28.203   c3.497,8.26,8.653,15.734,14.926,22.001c1.59,1.586,3.169,3.044,4.892,4.494c12.286,10.175,28.145,16.32,45.319,16.32h369.958   c17.18,0,33.108-6.145,45.323-16.384c1.718-1.386,3.305-2.844,4.891-4.43c6.27-6.267,11.425-13.741,14.994-22.001v-0.064   c3.769-8.653,5.812-18.171,5.812-28.138V126.087C512,121.399,511.543,116.762,510.678,112.275z M46.509,101.571   c6.345-6.338,14.866-10.175,24.512-10.175h369.958c9.646,0,18.242,3.837,24.512,10.175c1.122,1.129,2.179,2.387,3.112,3.637   L274.696,274.203c-5.348,4.687-11.954,7.002-18.696,7.002c-6.674,0-13.276-2.315-18.695-7.002L43.472,105.136   C44.33,103.886,45.387,102.7,46.509,101.571z M36.334,385.92V142.735L176.658,265.15L36.405,387.435   C36.334,386.971,36.334,386.449,36.334,385.92z M440.979,420.597H71.021c-6.281,0-12.158-1.651-17.174-4.552l147.978-128.959   l13.815,12.018c11.561,10.046,26.028,15.134,40.36,15.134c14.406,0,28.872-5.088,40.432-15.134l13.808-12.018l147.92,128.959   C453.137,418.946,447.26,420.597,440.979,420.597z M475.666,385.92c0,0.529,0,1.051-0.068,1.515L335.346,265.221L475.666,142.8   V385.92z"
                                                />
                                            </g>
                                        </svg>
                                        {{ item.MailAdress }}
                                    </a>
                                </div>
                                <a
                                    class="to-blog"
                                    v-bind:href="
                                        'https://blog.serpent-jp.com/author/' +
                                        item.name
                                    "
                                    >{{ item.name }} の書いたブログ記事を見る</a
                                >
                            </div>
                        </div>
                    </div>
                    <hr />
                </ul>
            </li>
            <b-pagination
                :total-rows="rows"
                v-model="currentPage"
                :per-page="perPage"
                :items="list"
                aria-controls="my-list"
                class="page-nation"
                small
                align="center"
            ></b-pagination>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data: () => {
        return {
            currentPage: 1,
            perPage: 5,
            list: [],
        };
    },
    mounted() {
        axios
            .get("https://serpent.pythonanywhere.com/api/author/")
            .then((response) => (this.list = response.data));
    },
    computed: {
        rows() {
            return this.list.length;
        },
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
    font-size: 50px;
    font-family: "Domine", serif;
}
.author-box {
    display: flex;
}
.author-box-detail {
    font-family: "M PLUS Rounded 1c", sans-serif;
    margin: 0 5%;
    min-width: 0;
    width: 90%;
}
.icon-outer-pc {
    max-width: 300px;
    max-height: 300px;
    min-width: 300px;
    min-height: 300px;
}
.icon {
    border-radius: 100%;
    width: 100%;
    height: 100%;
    box-shadow: 0 20px 30px #00000022, 0 6px 10px #00000022;
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
.meta-box-inner {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
}
.btn {
    white-space: nowrap;
    margin: 5px;
    color: white;
    font-weight: bold;
    font-size: 13px;
    line-height: 26px;
    padding: 5px;
    border-radius: 5px;
    box-shadow: 0 5px 10px #00000022, 0 6px 6px #00000022;
}
.btn:hover {
    text-decoration: none;
    color: white;
}
.btn-svg {
    width: 20px;
    fill: white;
}
/* .name-box {
    display: flex;
} */
.name {
    font-weight: bold;
    font-size: 25px;
    padding: 0 15px;
}
.homepage-button {
    background-color: rgb(240, 129, 44);
}
.homepage-button:hover {
    background-color: rgb(184, 98, 33);
}
.twitter-button {
    background-color: rgb(29, 161, 242);
}
.twitter-button:hover {
    background-color: rgb(22, 125, 189);
}
.instagram-button {
    background: radial-gradient(
            circle farthest-corner at 35% 90%,
            #fec564,
            transparent 50%
        ),
        radial-gradient(
            circle farthest-corner at 0 140%,
            #fec564,
            transparent 50%
        ),
        radial-gradient(
            ellipse farthest-corner at 0 -25%,
            #5258cf,
            transparent 50%
        ),
        radial-gradient(
            ellipse farthest-corner at 20% -50%,
            #5258cf,
            transparent 50%
        ),
        radial-gradient(
            ellipse farthest-corner at 100% 0,
            #893dc2,
            transparent 50%
        ),
        radial-gradient(
            ellipse farthest-corner at 60% -20%,
            #893dc2,
            transparent 50%
        ),
        radial-gradient(
            ellipse farthest-corner at 100% 100%,
            #d9317a,
            transparent
        ),
        linear-gradient(
            #6559ca,
            #bc318f 30%,
            #e33f5f 50%,
            #f77638 70%,
            #fec66d 100%
        );
}
.github-button {
    background-color: rgb(75, 75, 75);
}
.github-button:hover {
    background-color: rgb(36, 36, 36);
}
.qitta-button {
    background-color: rgb(95, 197, 0);
}
.qitta-button:hover {
    background-color: rgb(59, 121, 0);
}
.note-button {
    background-color: rgb(44, 182, 150);
}
.note-button:hover {
    background-color: rgb(25, 102, 84);
}
.hatena-button {
    background-color: rgb(167, 169, 168);
}
.hatena-button:hover {
    background-color: rgb(80, 82, 81);
}
.mailadress {
    background-color: rgb(238, 74, 74);
}
.mailadress:hover {
    background-color: rgb(189, 22, 22);
}
.to-blog {
    margin: 40px 0 0 40px;
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
    box-shadow: 0 10px 20px #00000022, 0 6px 6px #00000022;
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
.icon-outer-mobile {
    display: none;
}
.hr {
    display: block;
}
@media (max-width: 1000px) {
    .member-outer {
        padding: 0 2%;
    }
    .member-title {
        text-align: center;
        margin: 50px 0;
        font-size: 30px;
        font-family: "Domine", serif;
    }
    .icon-outer-pc {
        display: none;
    }
    .author-box {
        flex-direction: column;
    }
    .btn {
        font-size: 12px;
    }
    ul {
        padding: 0;
    }
    .to-blog {
        margin: 5px 0;
        width: 100%;
        text-align: center;
        max-width: 500px;
    }
    .btn-svg {
        width: 15px;
    }
    .meta-box {
        text-align: center;
    }
    .meta-box-inner {
        justify-content: space-around;
    }
    .icon {
        box-shadow: none;
    }
    .icon-outer-mobile {
        display: block;
        max-width: 60px;
        max-height: 60px;
        min-width: 60px;
        min-height: 60px;
    }
    .name-box {
        display: flex;
        margin-bottom: 10px;
    }
    .role {
        position: relative;
        height: min-content;
    }
    .name {
        height: min-content;
    }
    .hr {
        display: none;
    }
}
</style>
