<template>
    <header class="header fixed-top">	    
        <div class="branding docs-branding">
            <div class="container-fluid position-relative py-2">
                <div class="docs-logo-wrapper">

                  <slot name="sidebar-toggler"></slot>

	                <div class="site-logo"><NuxtLink class="navbar-brand" to="/"><span class="logo-text">ИЭТР <span class="text-alt">Спрвочник АТС</span></span></NuxtLink></div>    
                </div><!--//docs-logo-wrapper-->
	            <div class="docs-top-utilities d-flex justify-content-end align-items-center">

                <slot name="search-form"></slot>


	
					<ul class="social-list list-inline mx-md-3 mx-lg-5 mb-0 d-none d-lg-flex">
						<li class="list-inline-item"><a href="https://github.com/Slava191/transport_backend"><i class="fab fa-github fa-fw"></i></a></li>
		            </ul><!--//social-list-->
		            <a href="http://tehnopark-madi.ru/" class="btn btn-primary d-none d-lg-flex">Сайт проекта</a>
	            </div><!--//docs-top-utilities-->
            </div><!--//container-->
        </div><!--//branding-->
    </header><!--//header-->
</template>