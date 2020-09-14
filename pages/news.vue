<template>
    <div class="news-outer">
        <h1 class="news-title">News</h1>
        <div style="list-style:none">
            <li id="my-list">
                <ul
                    v-for="(item, index) in reverceList.slice(perPage * (currentPage - 1), perPage * currentPage)"
                    :key="index"
                >
                    <div class="news-card">
                        <img
                            class="news-thubnail"
                            v-bind:src="item.thumbnail"
                            v-bind:alt="item.title"
                        />
                        <div class="news-message">
                            <h2 class="news-message-title">
                                {{ item.title }}
                                <span class="date">{{ item.created_at | moment }}</span>
                            </h2>
                            <hr />
                            <p v-html="$md.render(item.content)"></p>
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
import moment from "moment";
export default {
    data: () => {
        return {
            currentPage: 1,
            perPage: 7,
            list: [],
        };
    },
    filters: {
        moment: function (date) {
            return moment(date).format("YYYY/MM/DD");
        },
    },
    mounted() {
        axios
            .get("https://serpent.pythonanywhere.com/api/news/")
            .then((response) => (this.list = response.data));
    },
    computed: {
        rows() {
            return this.list.length;
        },
        reverceList() {
            return this.list.reverse();
        },
    },
};
</script>

<style>
.news-title {
    font-size: 80px;
    margin: auto;
    text-align: center;
    font-family: "Domine", serif;
}
.news-outer {
    padding: 0 10%;
}
.news-card {
    display: flex;
    height: 200px;
}
.news-message {
    font-family: "M PLUS Rounded 1c", sans-serif;
    width: 90%;
    padding: 0 3%;
}
.news-message-title {
    padding-right: 120px;
    position: relative;
    font-size: 25px;
    font-weight: bold;
}
.news-thubnail {
    width: 300px;
}
.date {
    position: absolute;
    right: 0;
    font-size: 20px;
    background: #555;
    color: white;
    padding: 5px;
    border-radius: 5px;
}
</style>
