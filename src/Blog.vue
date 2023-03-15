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
      <form @submit.prevent="submit" class="form-horizontal">
        <div class="form-group">
          <label for="inputEmail3" class="col-sm-2 control-label">title</label>
          <div class="col-sm-10">
            <input
              v-model="title"
              type="text"
              class="form-control"
              id="inputEmail3"
              placeholder="Title"
            />
          </div>
        </div>
        <div class="form-group">
          <label for="inputPassword3" class="col-sm-2 control-label"
            >Body</label
          >
          <div class="col-sm-10">
            <textarea
              v-model="body"
              class="form-control"
              id="inputPassword3"
              placeholder="Body"
            ></textarea>
          </div>
        </div>
        <div class="form-group">
          <div class="col-sm-offset-2 col-sm-10">
            <button type="submit" class="btn btn-default">New Post</button>
          </div>
        </div>
      </form>
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
    async submit() {
      if (this.title == "" || this.body == "") return;
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ title: this.title, body: this.body ,user_id: 1 }),
      };
      const response = await fetch("http://127.0.0.1:8000/api/posts", requestOptions);
      const data = await response.json();
      if(response.status == 200){
        this.getData();
        this.title='';
        this.body='';
      }
    },
  },
  mounted() {
    this.getData();
  },
};
</script>
