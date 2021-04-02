<template>
    <nav id="docs-nav" class="docs-nav navbar">
        <ul class="section-items list-unstyled nav flex-column pb-3">
            <li class="nav-item section-title" v-for="item in docs" :key="item.slug" >
                <NuxtLink :to="`/ietm/${item.slug}`" class="nav-link scrollto active">
                    <span class="theme-icon-holder mr-2"><i class="fas fa-map-signs"></i></span>{{item.title}}
                </NuxtLink>  
            </li>
            <li class="nav-item section-title">
                <NuxtLink :to="`/diagnostic_dialogues`" class="nav-link scrollto active">
                    <span class="theme-icon-holder mr-2"><i class="fas fa-map-signs"></i></span>Устранение неисправностей
                </NuxtLink>  
            </li>
        </ul>
    </nav>
</template>
<script>
export default {
    data(){
        return{
            docs: []
        }
    },
    async fetch() {
        this.docs = await this.$content(`ietm`).only(['slug', 'title']).fetch() 
    }
}
</script>