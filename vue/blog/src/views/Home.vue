<template>
  <div class="home">
    <article v-for="article in articles">
        <h3 @click="routerToArticle(article.id)">{{ article.title }}</h3>
        <i>{{ article.date }}</i>
        <span>{{ article.content | subContent }}</span>
    </article>
  </div>
</template>

<script>

import axios from "axios";

export default {
    name: 'Home',
    mounted() {
        const api = "https://us-central1-expressapi-8c039.cloudfunctions.net/app/article";
        axios.get(api)
            .then(result => {
            // console.log(result.data);
            this.articles = result.data.data;
        });
    },
    data () {
        return {
            articles: [],
        }
    },
    methods: {
        routerToArticle: function(id) {
            this.$router.push({name: "Article", params: {id:id}})
        }
    },
    filters: {
        subContent: (content) => {
            return content.substring(0, 150);
        }
    }
}
</script>

<style lang="scss" scoped>
    article {
        width: 80vw;
        height: 200px;
        display: flex;
        padding: 2rem;
        justify-content: center;
        margin: 1rem;
        flex-direction: column;
        align-items: flex-start;
        background-color: #dddddd;
        border-radius: 16px;

        i {
            color: #cccccc;
        }
    }
</style>
