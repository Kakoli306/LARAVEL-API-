<template>
<div>
<h2>Articles</h2>
<div class="card card-body mb-2" v-for="article in articles" v-bind:key="article.id">

</div>
</div>

</template>


    
<script>
export default {
  data() {
    return {
      articles: [],
      article: {
        id: '',
        title: '',
        body: ''
      },
      article_id: '',
      pagination: {},
      edit: false
    };
  },
  created() {
    this.fetchArticles();
  },
  methods: {
        fetchArticles() {
            fetch('api/articles')
            .then(res => res.json())
            .then(res => {
                console.log(res.data);
            });
        }
    }
};


</script>

