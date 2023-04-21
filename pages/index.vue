<template>
  <div class="home-page">
	  <h2>Latest Posts</h2>
	  <div class="articles">
		  <div class="article" v-for="article of articles" :key="article">
			  <nuxt-link :to="{ name: 'slug', params: { slug: article.slug } }">
				  <div class="article-inner">
						<img :src="require(`~/assets/resources/${article.img}`)" alt="" />
						<div class="detail">
							<h3>{{ article.title }}</h3>
							<p>{{ article.description }}</p>
						</div>
				  </div>
			  </nuxt-link>
		  </div>
	  </div>
  </div>
</template>

<script>
export default {
	async asyncData({ $content, params }) {
		const articles = await $content('blog', params.slug)
			.only(['title', 'description', 'img', 'slug'])
			.sortBy('createdAt', 'asc')
			.fetch();

		return {
			articles
		}
	}
}
</script>

<style>

.home-page {
  padding: 50px 30px;
  background-color: #0f1729;
}

h2 {
  margin-bottom: 30px;
  text-align: center;
  background: #0EA6EC;
  background: linear-gradient(to right, #0EA6EC 36%, #BAE1F2 70%);
  background-clip: text;
  -webkit-text-fill-color: transparent;

}

.articles {
  margin: 0 auto;
  max-width: 800px;
}

.article {
  margin-bottom: 15px;
}

.article-inner {
  padding: 15px;
  box-shadow: 0 0 1rem 0 rgba(0, 0, 0, .2); 
  background-color: #131B30;
  backdrop-filter: blur(5px);
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  border: 1px solid #223044;

  display: flex;
}

.article-inner img {
  display: block;
  width: 100%;
  max-width: 200px;
}
.article-inner .detail {
  padding-left: 15px;
  padding-right: 15px;
}

h3 {
  color: #BAE1F2;
  font-size: 24px;
  text-decoration: none;
}

p {
  color: #92A8C8;
  font-size: 18px;
  text-decoration: none;
}
</style>
