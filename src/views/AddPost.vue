<template>
  <!--blog start-->
  <section id="blog" class="blog">
    <div class="container">
      <div class="blog-details">
        <div class="gallary-header text-center">
          <h2>Adding New Post</h2>
          <p></p>
        </div>
      </div>
      <section style="margin-top:20rem" class="travel-box">
        <div class="container">
          <div class="row">
            <div class="col-md-6 col-md-offset-3">
              <div class="single-travel-boxes">
                <div id="desc-tabs" class="desc-tabs">
                  <!-- <ul class="nav nav-tabs" role="tablist">
                    <li role="presentation" class="active">
                      <a
                        href="#tours"
                        aria-controls="tours"
                        role="tab"
                        data-toggle="tab"
                      >
                        <i class="fa fa-tree"></i>
                        tours
                      </a>
                    </li>
  
                    <li role="presentation">
                      <a
                        href="#hotels"
                        aria-controls="hotels"
                        role="tab"
                        data-toggle="tab"
                      >
                        <i class="fa fa-building"></i>
                        hotels
                      </a>
                    </li>
  
                    <li role="presentation">
                      <a
                        href="#flights"
                        aria-controls="flights"
                        role="tab"
                        data-toggle="tab"
                      >
                        <i class="fa fa-plane"></i>
                        flights
                      </a>
                    </li>
                  </ul> -->
  
                  <!-- Tab panes -->
                  <div class="tab-content">
                    <div
                      role="tabpanel"
                      class="tab-pane active fade in"
                      id="tours"
                    >
                      <div class="tab-para">
                        <form @submit.prevent="submit" class="form-horizontal">
                        <div class="row">
                          <div class="col-lg-12 col-md-12 col-sm-12">
                            <div class="single-tab-select-box">
                              <h2>title</h2>
                              <div class="form-group">
                                <input type="text" v-model="title" class="form-control" placeholder="Title">
                                
                              </div>
                              <!-- /.travel-select-icon -->
                              <h2>Body</h2>
                              <div class="form-group">
                                <textarea type="body" v-model="body" class="form-control" placeholder="Body">
                                  </textarea>
                                
                              </div>
                              <div class="clo-sm-7">
                                <div class="about-btn travel-mrt-0 pull-right">
                                  <button type="submit" class="about-view travel-btn">Add New</button
                                  ><!--/.travel-btn-->
                                </div></div>
                                <!--/.about-btn-->
                              <!-- /.travel-select-icon -->
                            </div>
                            <!--/.single-tab-select-box-->
                          </div>
                          <!--/.col-->
                          
                          
                          
                        </div>
                        <!--/.row-->
                        
                        
                      </form> 
                      </div>
                      <!--/.tab-para-->
                    </div>
                    <!--/.tabpannel-->
                  </div>
                  <!--/.tab content-->
                </div>
                <!--/.desc-tabs-->
              </div>
              <!--/.single-travel-box-->
            </div>
            <!--/.col-->
          </div>
          <!--/.row-->
        </div>
        <!--/.container-->
      </section>
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
      title: "",
      body: "",
    };
  },
  methods: {
    async submit() {
      if (this.title == "" || this.body == "") return;
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          title: this.title,
          body: this.body,
          user_id: 1,
        }),
      };
      const response = await fetch(
        "http://127.0.0.1:8000/api/posts",
        requestOptions
      );
      const data = await response.json();
      if (response.status == 200) {
        this.title = "";
        this.body = "";
        this.$router.push('blog');
      }
    },
  },
  mounted() {
    
  },
};
</script>
