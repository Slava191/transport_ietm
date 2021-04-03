<template>
    <div>

        <Header>
            
            <template v-slot:sidebar-toggler>
                <button id="docs-sidebar-toggler" class="docs-sidebar-toggler docs-sidebar-visible mr-2 d-xl-none" type="button">
                    <span></span>
                    <span></span>
                    <span></span>
                </button>
            </template>

            <template v-slot:search-form>
                <div class="top-search-box d-none d-lg-flex">
                    <form class="search-form">
                        <input type="text" placeholder="Search the docs..." name="search" class="form-control search-input">
                        <button type="submit" class="btn search-btn" value="Search"><i class="fas fa-search"></i></button>
                    </form>
                </div>
            </template>
            
        </Header>

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
		    
                <Footer/>
		    </div> 
	    </div>
    </div><!--//docs-wrapper-->

    </div>
</template>

<script>
import $ from '@/assets/plugins/jquery-3.4.1.min.js'
import Header from '~/components/Header.vue';
export default {
  components: { Header },
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
