<template>
    <div>
        <h1 class="privacy_policy-title">プライバシーポリシー</h1>
        <div class="privacy_policy" v-html="$md.render(content)"></div>
    </div>
</template>
<script>
import privacy_policy from "@/assets/content/privacy_policy.md";
export default {
    data() {
        return {
            content: `${privacy_policy}`,
        };
    },
};
</script>

<style>
.privacy_policy-title {
    text-align: center;
}
.privacy_policy {
    padding: 0 10% 100px 10%;
}
.privacy_policy h1 {
    border-left: 20px rgb(255, 221, 167) solid;
    padding: 10px 30px;
    border-bottom: 1px gray solid;
    margin: 30px 0;
}
.privacy_policy h1:first-child {
    margin: 40px 0 30px 0;
}
.privacy_policy p,
.privacy_policy ul {
    margin: 0 30px;
}
@media (max-width: 1000px) {
    .privacy_policy-title {
        font-size: 30px;
    }
    .privacy_policy {
        padding: 0 3%;
    }
    .privacy_policy h1 {
        font-size: 25px;
        padding: 0 3px;
        border-left: 10px rgb(255, 221, 167) solid;
    }
}
</style>
