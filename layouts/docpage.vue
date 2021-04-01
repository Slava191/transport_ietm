<template>
    <div>
    <header class="header fixed-top">	    
        <div class="branding docs-branding">
            <div class="container-fluid position-relative py-2">
                <div class="docs-logo-wrapper">
					<button id="docs-sidebar-toggler" class="docs-sidebar-toggler docs-sidebar-visible mr-2 d-xl-none" type="button">
	                    <span></span>
	                    <span></span>
	                    <span></span>
	                </button>
	                <div class="site-logo"><NuxtLink class="navbar-brand" to="/"><span class="logo-text">ИЭТР <span class="text-alt">Спрвочник АТС</span></span></NuxtLink></div>    
                </div><!--//docs-logo-wrapper-->
	            <div class="docs-top-utilities d-flex justify-content-end align-items-center">
	                <div class="top-search-box d-none d-lg-flex">
		                <form class="search-form">
				            <input type="text" placeholder="Search the docs..." name="search" class="form-control search-input">
				            <button type="submit" class="btn search-btn" value="Search"><i class="fas fa-search"></i></button>
				        </form>
	                </div>
	
					<ul class="social-list list-inline mx-md-3 mx-lg-5 mb-0 d-none d-lg-flex">
						<li class="list-inline-item"><a href="#"><i class="fab fa-github fa-fw"></i></a></li>
			            <li class="list-inline-item"><a href="#"><i class="fab fa-twitter fa-fw"></i></a></li>
		                <li class="list-inline-item"><a href="#"><i class="fab fa-slack fa-fw"></i></a></li>
		                <li class="list-inline-item"><a href="#"><i class="fab fa-product-hunt fa-fw"></i></a></li>
		            </ul><!--//social-list-->
		            <a href="https://themes.3rdwavemedia.com/bootstrap-templates/startup/coderdocs-free-bootstrap-4-documentation-template-for-software-projects/" class="btn btn-primary d-none d-lg-flex">Download</a>
	            </div><!--//docs-top-utilities-->
            </div><!--//container-->
        </div><!--//branding-->
    </header><!--//header-->

        <div class="docs-wrapper">
	    <div id="docs-sidebar" class="docs-sidebar">
		    <div class="top-search-box d-lg-none p-3">
                <form class="search-form">
		            <input type="text" placeholder="Search the docs..." name="search" class="form-control search-input">
		            <button type="submit" class="btn search-btn" value="Search"><i class="fas fa-search"></i></button>
		        </form>
            </div>
            <Nav/><!--//docs-nav-->
	    </div><!--//docs-sidebar-->
	    <div class="docs-content">
		    <div class="container">
			    <article class="docs-article" id="section-1">

                    <Nuxt/>
					
			    </article>
		    
				<footer class="footer">
				    <div class="container text-center py-5">
					    <!--/* This template is free as long as you keep the footer attribution link. If you'd like to use the template without the attribution link, you can buy the commercial license via our website: themes.3rdwavemedia.com Thank you for your support. :) */-->
				        <small class="copyright">Designed with <i class="fas fa-heart" style="color: #fb866a;"></i> by <a class="theme-link" href="http://themes.3rdwavemedia.com" target="_blank">Xiaoying Riley</a> for developers</small>
				        <ul class="social-list list-unstyled pt-4 mb-0">
						    <li class="list-inline-item"><a href="#"><i class="fab fa-github fa-fw"></i></a></li> 
				            <li class="list-inline-item"><a href="#"><i class="fab fa-twitter fa-fw"></i></a></li>
				            <li class="list-inline-item"><a href="#"><i class="fab fa-slack fa-fw"></i></a></li>
				            <li class="list-inline-item"><a href="#"><i class="fab fa-product-hunt fa-fw"></i></a></li>
				            <li class="list-inline-item"><a href="#"><i class="fab fa-facebook-f fa-fw"></i></a></li>
				            <li class="list-inline-item"><a href="#"><i class="fab fa-instagram fa-fw"></i></a></li>
				        </ul><!--//social-list-->
				    </div>
			    </footer>
		    </div> 
	    </div>
    </div><!--//docs-wrapper-->

    </div>
</template>

<script>
import $ from '@/assets/plugins/jquery-3.4.1.min.js'
export default {
    mounted(){
        
$(window).on('load resize', function() {
   
        //Add/remove class based on browser size when load/resize
        var w = $(window).width();

        if(w >= 1200) {
            // if larger 
            $('#docs-sidebar').addClass('sidebar-visible').removeClass('sidebar-hidden');
        } else {
            // if smaller
            $('#docs-sidebar').addClass('sidebar-hidden').removeClass('sidebar-visible');
        }
    });


    $(document).ready(function() {
        
        /* ====== Toggle Sidebar ======= */
        
        $('#docs-sidebar-toggler').on('click', function(){
        
            if ( $('#docs-sidebar').hasClass('sidebar-visible') ) {

                $("#docs-sidebar").removeClass('sidebar-visible').addClass('sidebar-hidden');
                
                
            } else {

                $("#docs-sidebar").removeClass('sidebar-hidden').addClass('sidebar-visible');
                
            }
                
        });
        

        /* ====== Activate scrollspy menu ===== */
        //$('body').scrollspy({target: '#docs-nav', offset: 100});
        
        
        
        /* ===== Smooth scrolling ====== */
        // $('#docs-sidebar a.scrollto').on('click', function(e){
        //     //store hash
        //     var target = this.hash;    
        //     e.preventDefault();
        //     $('body').scrollTo(target, 800, {offset: -69, 'axis':'y'});
            
        //     //Collapse sidebar after clicking
        //     if ($('#docs-sidebar').hasClass('sidebar-visible') && $(window).width() < 1200){
        //         $('#docs-sidebar').removeClass('sidebar-visible').addClass('slidebar-hidden');
        //     }
            
        // });
        
        /* wmooth scrolling on page load if URL has a hash */
        // if(window.location.hash) {
        //     var urlhash = window.location.hash;
        //     $('body').scrollTo(urlhash, 800, {offset: -69, 'axis':'y'});
        // }
        
        
        /* Bootstrap lightbox */
        /* Ref: http://ashleydw.github.io/lightbox/ */

        // $(document).delegate('*[data-toggle="lightbox"]', 'click', function(e) {
        //     e.preventDefault();
        //     $(this).ekkoLightbox();
        // }); 

        
        

    });
    }
}
</script>
