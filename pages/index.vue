<template>
<div>
      <div class="page-header theme-bg-dark py-5 text-center position-relative">
	    <div class="theme-bg-shapes-right"></div>
	    <div class="theme-bg-shapes-left"></div>
	    <div class="container">
		    <h1 class="page-heading single-col-max mx-auto">ИЭТР к справочнику АТС</h1>
		    <div class="page-intro single-col-max mx-auto">Интерактивные электронные технические руководства</div>
		    <!-- <div class="main-search-box pt-3 d-block mx-auto">
                 <form class="search-form w-100">
		            <input type="text" placeholder="Search the docs..." name="search" class="form-control search-input">
		            <button type="submit" class="btn search-btn" value="Search"><i class="fas fa-search"></i></button>
		        </form>
             </div> -->
	    </div>
    </div><!--//page-header-->
    <div class="page-content">
	    <div class="container">
		    <div class="docs-overview py-5">
			    <div class="row justify-content-center">
				    <div class="col-12 col-lg-4 py-3" v-for="item in docs" :key="item.slug">
					    <div class="card shadow-sm">
						    <div class="card-body">
							    <h5 class="card-title mb-3">
								    <span class="theme-icon-holder card-icon-holder mr-2">
								        <i :class="item.icon"></i>
							        </span><!--//card-icon-holder-->
							        <span class="card-title-text">{{item.title}}</span>
							    </h5>
							    <div class="card-text">
								    {{item.description}}
							    </div>
							    <a class="card-link-mask" :href="`/ietm/${item.slug}`"></a>
						    </div><!--//card-body-->
					    </div><!--//card-->
				    </div><!--//col-->
					<div class="col-12 col-lg-4 py-3">
					    <div class="card shadow-sm">
						    <div class="card-body">
							    <h5 class="card-title mb-3">
								    <span class="theme-icon-holder card-icon-holder mr-2">
								        <i class="fas fa-bug"></i>
							        </span><!--//card-icon-holder-->
							        <span class="card-title-text">Устранение неполадок</span>
							    </h5>
							    <div class="card-text">
								    Возможные неисправности по работе с приложением и рекомендации по их устранению 
							    </div>
							    <a class="card-link-mask" :href="`/diagnostic_dialogues`"></a>
						    </div><!--//card-body-->
					    </div><!--//card-->
				    </div><!--//col-->
			    </div><!--//row-->
		    </div><!--//container-->
		</div><!--//container-->
    </div><!--//page-content-->

    <section class="cta-section text-center py-5 theme-bg-dark position-relative">
	    <div class="theme-bg-shapes-right"></div>
	    <div class="theme-bg-shapes-left"></div>
	    <div class="container">
		    <h3 class="mb-2 text-white mb-3">ООО МИП “ТЕХНОПАРК МАДИ”</h3>
		    <div class="section-intro text-white mb-3 single-col-max mx-auto">
				Справочник автотранспортной техники был разработан командой проекта ООО МИП "ТЕХНОПАРК МАДИ" в рамках создания
				цифровой платформы поддержки принятия решений для обеспечения перевозок крупногабаритных и тяжелых грузов
			</div>
		    <div class="pt-3 text-center">
			    <a class="btn btn-light" href="http://tehnopark-madi.ru/">Наш сайт<i class="fas fa-arrow-alt-circle-right ml-2"></i></a>
		    </div>
	    </div>
    </section>
	<!--//cta-section-->

            
	<Footer/>

</div>
</template>

<script>
export default {
    async asyncData({ $content}){
        const docs = await $content(`ietm`).only(['slug', 'title', 'icon', 'description']).fetch()
        return { docs }
    }
}
</script>


