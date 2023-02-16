<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="top-area">
    <div class="header-area">
      <div class="container">
        <div class="row">
          <div class="col-sm-2">
            <div class="logo">
              <a href="index.html">
                tour<span>Nest</span>
              </a>
            </div><!-- /.logo-->
          </div><!-- /.col-->
          <div class="col-sm-10">
            <div class="main-menu">
            
              <!-- Brand and toggle get grouped for better mobile display -->
              <div class="navbar-header">
                <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
                  <i class="fa fa-bars"></i>
                </button><!-- / button-->
              </div><!-- /.navbar-header-->
              <div class="collapse navbar-collapse">		  
                <ul class="nav navbar-nav navbar-right">
                  <li class="smooth-menu"><RouterLink to="/">home</RouterLink></li>
                  <li class="smooth-menu"><RouterLink to="/destination">Destination</RouterLink></li> 
                  <li class="smooth-menu"><RouterLink to="/packages">Packages</RouterLink></li>
                  <li class="smooth-menu"><RouterLink to="/specialoffers">Special Offers</RouterLink></li>
                  <li class="smooth-menu"><RouterLink to="/blog">blog</RouterLink></li>
                  
                  <li>
                    <button class="book-btn">book now
                    </button>
                  </li><!--/.project-btn--> 
                </ul>
              </div><!-- /.navbar-collapse -->
            </div><!-- /.main-menu-->
          </div><!-- /.col-->
        </div><!-- /.row -->
        <div class="home-border"></div><!-- /.home-border-->
      </div><!-- /.container-->
    </div><!-- /.header-area -->

  </header><!-- /.top-area-->
  <!-- main-menu End -->
  <!--about-us start -->
  

  <RouterView />
   <!--subscribe start-->
   <section id="subs" class="subscribe">
    <div class="container">
      <div class="subscribe-title text-center">
        <h2>
          Join our Subscribers List to Get Regular Update
        </h2>
        <p>
          Subscribe Now. We will send you Best offer for your Trip 
        </p>
      </div>
      <form>
        <div class="row">
          <div class="col-md-6 col-md-offset-3 col-sm-8 col-sm-offset-2">
            <div class="custom-input-group">
              <input type="email" class="form-control" placeholder="Enter your Email Here">
              <button class="appsLand-btn subscribe-btn">Subscribe</button>
              <div class="clearfix"></div>
              <i class="fa fa-envelope"></i>
            </div>

          </div>
        </div>
      </form>
    </div>

  </section>
  <!--subscribe end-->
  <!-- footer-copyright start -->
  <footer  class="footer-copyright">
    <div class="container">
      <div class="footer-content">
        <div class="row">

          <div class="col-sm-3">
            <div class="single-footer-item">
              <div class="footer-logo">
                <a href="index.html">
                  tour<span>Nest</span>
                </a>
                <p>
                  best travel agency
                </p>
              </div>
            </div><!--/.single-footer-item-->
          </div><!--/.col-->

          <div class="col-sm-3">
            <div class="single-footer-item">
              <h2>link</h2>
              <div class="single-footer-txt">
                <p><a href="#">home</a></p>
                <p><a href="#">destination</a></p>
                <p><a href="#">spacial packages</a></p>
                <p><a href="#">special offers</a></p>
                <p><a href="#">blog</a></p>
                <p><a href="#">contacts</a></p>
              </div><!--/.single-footer-txt-->
            </div><!--/.single-footer-item-->

          </div><!--/.col-->

          <div class="col-sm-3">
            <div class="single-footer-item">
              <h2>popular destination</h2>
              <div class="single-footer-txt">
                <p><a href="#">china</a></p>
                <p><a href="#">venezuela</a></p>
                <p><a href="#">brazil</a></p>
                <p><a href="#">australia</a></p>
                <p><a href="#">london</a></p>
              </div><!--/.single-footer-txt-->
            </div><!--/.single-footer-item-->
          </div><!--/.col-->

          <div class="col-sm-3">
            <div class="single-footer-item text-center">
              <h2 class="text-left">contacts</h2>
              <div class="single-footer-txt text-left">
                <p>+1 (300) 1234 6543</p>
                <p class="foot-email"><a href="#">info@tnest.com</a></p>
                <p>North Warnner Park 336/A</p>
                <p>Newyork, USA</p>
              </div><!--/.single-footer-txt-->
            </div><!--/.single-footer-item-->
          </div><!--/.col-->

        </div><!--/.row-->

      </div><!--/.footer-content-->
      <hr>
      <div class="foot-icons ">
        <ul class="footer-social-links list-inline list-unstyled">
                  <li><a href="#" target="_blank" class="foot-icon-bg-1"><i class="fa fa-facebook"></i></a></li>
                  <li><a href="#" target="_blank" class="foot-icon-bg-2"><i class="fa fa-twitter"></i></a></li>
                  <li><a href="#" target="_blank" class="foot-icon-bg-3"><i class="fa fa-instagram"></i></a></li>
            </ul>
            <p>&copy; 2017 <a href="https://www.themesine.com">ThemeSINE</a>. All Right Reserved</p>

          </div><!--/.foot-icons-->
      <div id="scroll-Top">
        <i class="fa fa-angle-double-up return-to-top" id="scroll-top" data-toggle="tooltip" data-placement="top" title="" data-original-title="Back to Top" aria-hidden="true"></i>
      </div><!--/.scroll-Top-->
    </div><!-- /.container-->

  </footer><!-- /.footer-copyright-->
  <!-- footer-copyright end -->

</template>