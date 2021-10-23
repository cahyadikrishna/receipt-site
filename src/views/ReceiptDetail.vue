<script>
export default {
  props: {
    category: { type: String, default: "" },
    image: { type: String, default: "" },
    mealname: { type: String, default: "" },
    area: { type: String, default: "" },
    instructions: { type: String, default: "" },
  },
  setup() {},
};
</script>

<template>
  <div class="row align-items-start">
    <div class="col-lg-8 m-15px-tb">
      <article class="article">
        <div class="article-img">
          <img
            class="card-img"
            :src="image"
            :title="mealname"
            alt="receipt pic"
          />
        </div>
        <div class="article-title">
          <router-link class="sub" :to="`/menu/${category}`">{{
            category
          }}</router-link>
          <h2>{{ mealname }}</h2>
          <h5>{{ area }}</h5>
        </div>
        <div class="article-content">
          <p>
            {{ instructions }}
          </p>
        </div>
      </article>
    </div>
    <div class="col-lg-4 m-15px-tb blog-aside">
      <!-- Latest Post -->
      <div class="widget widget-latest-post">
        <div class="widget-title">
          <h3>Latest Post</h3>
        </div>
        <div class="widget-body">
          <div class="latest-post-aside media">
            <div class="lpa-left media-body">
              <div class="lpa-title">
                <h5>
                  <a href="#">Prevent 75% of visitors from google analytics</a>
                </h5>
              </div>
              <div class="lpa-meta">
                <a class="name" href="#"> Rachel Roth </a>
                <a class="date" href="#"> 26 FEB 2020 </a>
              </div>
            </div>
            <div class="lpa-right">
              <a href="#">
                <img
                  src="https://via.placeholder.com/400x200/FFB6C1/000000"
                  title=""
                  alt=""
                />
              </a>
            </div>
          </div>
          <div class="latest-post-aside media">
            <div class="lpa-left media-body">
              <div class="lpa-title">
                <h5>
                  <a href="#">Prevent 75% of visitors from google analytics</a>
                </h5>
              </div>
              <div class="lpa-meta">
                <a class="name" href="#"> Rachel Roth </a>
                <a class="date" href="#"> 26 FEB 2020 </a>
              </div>
            </div>
            <div class="lpa-right">
              <a href="#">
                <img
                  src="https://via.placeholder.com/400x200/FFB6C1/000000"
                  title=""
                  alt=""
                />
              </a>
            </div>
          </div>
          <div class="latest-post-aside media">
            <div class="lpa-left media-body">
              <div class="lpa-title">
                <h5>
                  <a href="#">Prevent 75% of visitors from google analytics</a>
                </h5>
              </div>
              <div class="lpa-meta">
                <a class="name" href="#"> Rachel Roth </a>
                <a class="date" href="#"> 26 FEB 2020 </a>
              </div>
            </div>
            <div class="lpa-right">
              <a href="#">
                <img
                  src="https://via.placeholder.com/400x200/FFB6C1/000000"
                  title=""
                  alt=""
                />
              </a>
            </div>
          </div>
        </div>
      </div>
      <!-- End Latest Post -->
    </div>
  </div>
</template>

<style>
body {
  margin-top: 20px;
}
/* Blog Sidebar
-------------------*/
.blog-aside .widget {
  box-shadow: 0 0 30px rgba(31, 45, 61, 0.125);
  border-radius: 5px;
  overflow: hidden;
  background: #ffffff;
  margin-top: 15px;
  margin-bottom: 15px;
  width: 100%;
  display: inline-block;
  vertical-align: top;
}
.blog-aside .widget-body {
  padding: 15px;
}
.blog-aside .widget-title {
  padding: 15px;
  border-bottom: 1px solid #eee;
}
.blog-aside .widget-title h3 {
  font-size: 20px;
  font-weight: 700;
  color: #fc5356;
  margin: 0;
}
.blog-aside .latest-post-aside + .latest-post-aside {
  border-top: 1px solid #eee;
  padding-top: 15px;
  margin-top: 15px;
}
.blog-aside .latest-post-aside .lpa-right {
  width: 90px;
}
.blog-aside .latest-post-aside .lpa-right img {
  border-radius: 3px;
}
.blog-aside .latest-post-aside .lpa-left {
  padding-right: 15px;
}
.blog-aside .latest-post-aside .lpa-title h5 {
  margin: 0;
  font-size: 15px;
}
.blog-aside .latest-post-aside .lpa-title a {
  color: #20247b;
  font-weight: 600;
}
.blog-aside .latest-post-aside .lpa-meta a {
  color: #6f8ba4;
  font-size: 12px;
  text-transform: uppercase;
  display: inline-block;
  margin-right: 10px;
}
.article {
  box-shadow: 0 0 30px rgba(31, 45, 61, 0.125);
  border-radius: 5px;
  overflow: hidden;
  background: #ffffff;
  padding: 15px;
  margin: 15px 0 30px;
}
.article .article-title {
  padding: 15px 0 20px;
}
.article .article-title h6 {
  font-size: 14px;
  font-weight: 700;
  margin-bottom: 20px;
}
.article .article-title .sub {
  font-size: 1rem;
  text-transform: uppercase;
  color: #fc5356;
  border-bottom: 1px solid #fc5356;
}
.article .article-title h2 {
  color: #42b883;
  font-weight: 600;
}
img {
  max-width: 100%;
}
img {
  vertical-align: middle;
  border-style: none;
}
</style>
