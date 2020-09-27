<template>
    <div class="contact">
        <form id="app" class="form" @submit="onSubmit" method="post">
            <h1 class="page-title">Contact</h1>
            <p>
                <input
                    class="input-small"
                    name="username"
                    v-model="form.username"
                    type="text"
                    placeholder="お名前"
                />
            </p>
            <p>
                <input
                    class="input-small"
                    name="email"
                    v-model="form.email"
                    type="email"
                    placeholder="メールアドレス"
                />
            </p>
            <p>
                <input
                    class="input-small"
                    name="subject"
                    v-model="form.subject"
                    type="text"
                    placeholder="件名"
                />
            </p>
            <p>
                <textarea
                    class="input-big"
                    name="contents"
                    v-model="form.contents"
                    cols="30"
                    rows="5"
                    placeholder="ご用件"
                ></textarea>
            </p>
            <input type="submit" name="submit" value="Submit →" />
        </form>
    </div>
</template>

<script>
const querystring = require("querystring");

export default {
    data() {
        return {
            sent: false,
            form: {
                username: "",
                email: "",
                subject: "",
                contents: "",
            },
        };
    },
    methods: {
        onSubmit(e) {
            if (
                !this.username ||
                !this.email ||
                !this.subject ||
                !this.contents
            ) {
                alert("記入漏れがあります。全てご記入お願いします。");
            } else {
                e.preventDefault();
                this.$axios
                    .post(
                        "https://serpent.pythonanywhere.com/api/contact/",
                        querystring.stringify(this.form)
                    )
                    .then((res) => {
                        this.sent = true;
                        alert("送信に成功しました");
                    })
                    .catch(function (error) {
                        if (error.response) {
                            alert("送信に失敗しました。");
                        }
                    });
            }
        },
    },
};
</script>

<style>
.page-title {
    font-size: 80px;
    margin: auto;
    text-align: center;
    font-family: "Domine", serif;
    -moz-text-shadow: 5px 3px 5px rgba(255, 255, 255, 0.5);
    -webkit-text-shadow: 5px 3px 5px rgba(255, 255, 255, 0.5);
    -ms-text-shadow: 5px 3px 5px rgba(255, 255, 255, 0.5);
    text-shadow: 5px 3px 5px rgba(255, 255, 255, 0.5);
}
.contact {
    text-align: center;
}
.form {
    width: 60%;
    margin: 50px auto;
    padding: 3% 10%;
    background-size: 100%;
    border-radius: 10px;
}
.input-small,
.input-big {
    font-weight: 500;
    background-color: rgba(255, 255, 255, 0.5);
    padding: 5px;
    border-radius: 5px;
    color: gray;
    bottom: 0px;
    outline: none;
    border-style: solid;
    border-color: #e3e7ea;
    border-width: 0px 0px 2px 0px;
    font-size: 20px;
    -webkit-transition: 0.45s linear;
    transition: 0.45s linear;
}
.input-small:focus,
.input-big:focus {
    border-color: rgba(0, 251, 230, 0.726);
}
input[name="submit"] {
    border: none;
    letter-spacing: 4px;
    background-color: #ff0055;
    font-size: 30px;
    color: white;
    font-weight: 400;
    width: min-content;
    padding: 5px 30px;
    border-radius: 100px;
    box-shadow: 0 10px 20px #ff005571, 0 6px 6px #ff005571;
    outline: none;
}
input,
textarea {
    width: 100%;
}
@media (max-width: 1000px) {
    .page-title {
        font-size: 50px;
    }
    #app {
        margin: 0;
        width: 100%;
    }
}
</style>
