<template>
  <section>
  <script src="https://kit.fontawesome.com/4faac6e63e.js" crossorigin="anonymous"></script>
  <section>
      <div class="columns">
        <div  class="column main-text">
          <h1>Welcome to my Blog</h1>
      </div>
      </div>
  </section>

  <section>
    <template v-for="post in posts">
      <div :key="post.id" class="col-lg-3 col-md-4 col-sm-6 mb-4">
        <post :recipe="post"></post>
      </div>
    </template>
  </section>

  <div style="padding-bottom: 100px;"></div>
  </section> 
</template>


<script>
import Post from "~/components/Post.vue";

const sampleData = [
  {
    id: 1,
    title: "Jollof Rice",
    picture: "assets/css/bridge.jpg",
    category: "Cloud"
  }
];

export default {
  layout: "navbar",
  head() {
    return {
      title: "Recipes list"
    };
  },
  components: {
    Post
  },
  asyncData(context) {
    let data = sampleData;
    return {
      posts: data
    };
  },
  data(){
    return{
      posts: []
    }
  },
head: {
  meta: [
    { charset: 'utf-8' },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link:[{
    href: 'https://fonts.googleapis.com/css2?family=Spartan:wght@400;700&display=swap', rel: "stylesheet"
  }]
},

}
</script>
