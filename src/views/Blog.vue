<template>
  <!--blog start-->
  <section id="blog" class="blog">
    <div class="container">
      <div class="blog-details">
        <div class="gallary-header text-center">
          <h2>latest news</h2>
          <p>Travel News from all over the world</p>
        </div>
        <!--/.gallery-header-->
        <div class="blog-content">
          <div class="row">
            <div v-for="item in listItems" class="col-sm-4 col-md-4">
              <div class="thumbnail">
                <h2>
                  trending news <span>{{ formatDate(item.created_at) }}</span>
                </h2>
                <div class="thumbnail-img">
                  <img src="/src/assets/images/blog/b1.jpg" alt="blog-img" />
                  <div class="thumbnail-img-overlay"></div>
                  <!--/.thumbnail-img-overlay-->
                </div>
                <!--/.thumbnail-img-->

                <div class="caption">
                  <div class="blog-txt">
                    <h3>
                      <a href="#">
                        {{ item.title }}
                      </a>
                    </h3>
                    <p>
                      {{ item.body }}
                    </p>
                    <a href="#">Read More</a>
                  </div>
                  <!--/.blog-txt-->
                </div>
                <!--/.caption-->
              </div>
              <!--/.thumbnail-->
            </div>
            <!--/.col-->
          </div>
          <!--/.row-->
        </div>
        <!--/.blog-content-->
      </div>
      <!--/.blog-details-->
      <div class="clo-sm-7">
        <div class="about-btn travel-mrt-0 pull-right">
          <button @click="submit" class="about-view travel-btn">Add New</button
          ><!--/.travel-btn-->
        </div></div>
    </div>
    <!--/.container-->
  </section>
  <!--/.blog-->
  <!--blog end-->
</template>
<script>
import dayjs from "dayjs";

export default {
  data() {
    return {
      listItems: [],
      title: "",
      body: "",
    };
  },
  methods: {
    async getData() {
      const res = await fetch("http://127.0.0.1:8000/api/posts");
      const finalRes = await res.json();
      this.listItems = finalRes;
    },
    formatDate(dateString) {
      const date = dayjs(dateString);
      // Then specify how you want your dates to be formatted
      return date.format("D MMMM YYYY");
    },
     submit() {
      this.$router.push('addpost');
    },
  },
  mounted() {
    this.getData();
  },
};
</script>
