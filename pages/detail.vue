
<template>
  <div class="mt-5">
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="card col-md-6">
            <img :src="dataCurrentNews.urlToImage" alt="Card image cap" class="img-fluid">
            <p class="card-text"><small class="text-muted">{{ dataCurrentNews.publishedAt }} - {{ dataCurrentNews.author }}</small></p>
            <h5 class="card-title">{{ dataCurrentNews.title }}</h5>
            <p class="card-text">{{ dataCurrentNews.description }}</p>
            <p>
                sumber:
                <a :href="dataCurrentNews.url">{{ dataCurrentNews.url }}</a>
            </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return  {
            dataCurrentNews: {}
        }
    },
    mounted() {
        this.getDataCurrentNews()
    },
    methods: {
        getDataCurrentNews() {
            this.dataCurrentNews = JSON.parse(localStorage.getItem('CurrentNews'))
        }
    }
}
</script>

<style>

.img-fluid {
    object-fit: cover;
}

@media (max-width: 768px) {  
  .card {
    width: 100%;
  }
}


</style>