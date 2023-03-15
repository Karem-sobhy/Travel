<script>
// export default {
//   mounted() {
//     var owl = $("#testemonial-carousel");
//     owl.owlCarousel({
//       items: 3,
//       margin: 0,
//       loop: true,
//       autoplay: true,
//       smartSpeed: 1000,

//       //nav:false,
//       //navText:["<i class='fa fa-angle-left'></i>","<i class='fa fa-angle-right'></i>"],

//       dots: true,
//       autoplayHoverPause: true,

//       responsiveClass: true,
//       responsive: {
//         0: {
//           items: 1,
//         },
//         640: {
//           items: 1,
//         },
//         767: {
//           items: 2,
//         },
//         992: {
//           items: 3,
//         },
//       },
//     });
//   },
// };
export default {
    data() {
      return {
        listItems: []
      }
    },
    methods: {
      async getData() {
        const res = await fetch("http://127.0.0.1:8000/api/packages");
        const finalRes = await res.json();
        this.listItems = finalRes;
      }
    },
    mounted() {
      this.getData();
    }
  }
</script>
<template>
  <!--packages start-->
  <section id="pack" class="packages">
    <div class="container">
      <div class="gallary-header text-center">
        <h2>special packages</h2>
        <p>
          Duis aute irure dolor in velit esse cillum dolore eu fugiat nulla.
        </p>
      </div>
      <!--/.gallery-header-->
      <div class="packages-content">
        <div class="row">
          <div v-for="item in listItems" class="col-md-4 col-sm-6">
            <div class="single-package-item">
              <img
                src="/src/assets/images/packages/p1.jpg"
                alt="package-place"
              />
              <div class="single-package-item-txt">
                <h3>{{ item.name }} <span class="pull-right">${{ item.price }}</span></h3>
                <div class="packages-para">
                  <p>
                    {{ item.description }}
                  </p>
                </div>
                <!--/.packages-para-->
                <div class="packages-review">
                  <p>
                    <i class="fa fa-star"></i>
                    <i class="fa fa-star"></i>
                    <i class="fa fa-star"></i>
                    <i class="fa fa-star"></i>
                    <i class="fa fa-star"></i>
                    <span>{{ item.reviews }} review</span>
                  </p>
                </div>
                <!--/.packages-review-->
                <div class="about-btn">
                  <button class="about-view packages-btn">book now</button>
                </div>
                <!--/.about-btn-->
              </div>
              <!--/.single-package-item-txt-->
            </div>
            <!--/.single-package-item-->
          </div>
          <!--/.col-->
        </div>
        <!--/.row-->
      </div>
      <!--/.packages-content-->
    </div>
    <!--/.container-->
  </section>
  <!--/.packages-->
  <!--packages end-->

  <!-- testemonial Start -->
  <section class="testemonial">
    <div class="container">
      <div class="gallary-header text-center">
        <h2>clients reviews</h2>
        <p>
          Duis aute irure dolor in velit esse cillum dolore eu fugiat nulla.
        </p>
      </div>
      <!--/.gallery-header-->

      <div class="owl-carousel owl-theme" id="testemonial-carousel">
        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial1.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial2.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial1.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial1.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial2.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial1.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial1.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial2.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->

        <div class="home1-testm item">
          <div class="home1-testm-single text-center">
            <div class="home1-testm-img">
              <img src="/src/assets/images/client/testimonial1.jpg" alt="img" />
            </div>
            <!--/.home1-testm-img-->
            <div class="home1-testm-txt">
              <span class="icon section-icon">
                <i class="fa fa-quote-left" aria-hidden="true"></i>
              </span>
              <p>
                Lorem ipsum dolor sit amet, contur adip elit, sed do mod incid
                ut labore et dolore magna aliqua. Ut enim ad minim veniam.
              </p>
              <h3>
                <a href="#"> kevin watson </a>
              </h3>
              <h4>london, england</h4>
            </div>
            <!--/.home1-testm-txt-->
          </div>
          <!--/.home1-testm-single-->
        </div>
        <!--/.item-->
      </div>
      <!--/.testemonial-carousel-->
    </div>
    <!--/.container-->
  </section>
  <!--/.testimonial-->
  <!-- testemonial End -->
</template>
