<template>
    <nav id="docs-nav" class="docs-nav navbar">
        <ul class="section-items list-unstyled nav flex-column pb-3">
            <li class="nav-item section-title" v-for="item in docs" :key="item.slug" >
                <NuxtLink :to="`/ietm/${item.slug}`" class="nav-link" :class="{'active': isRouteActive(`/ietm/${item.slug}`)}">
                    <span class="theme-icon-holder mr-2"><i :class="item.icon"></i></span>{{item.title}}
                </NuxtLink>  
            </li>
            <li class="nav-item section-title">
                <NuxtLink 
                    :to="`/diagnostic_dialogues`" 
                    class="nav-link"
                    :class="{'active': isRouteActive(`/diagnostic_dialogues`)}"
                >
                    <span class="theme-icon-holder mr-2"><i class="fas fa-bug"></i></span>Устранение неисправностей
                </NuxtLink>  
            </li>
            <li class="nav-item"  v-for="item in dialogues" :key="item.slug">
                <NuxtLink class="nav-link" :class="{'active': isRouteActive(`/diagnostic_dialogues/${item.slug}`)}" :to="`/diagnostic_dialogues/${item.slug}`">{{item.title}}</NuxtLink>
            </li>
        </ul>
    </nav>
</template>
<script>
export default {
    data(){
        return{
            docs: [],
            dialogues: []
        }
    },
    methods: {
        isRouteActive(id) {
            if (this.$route.path.includes(id)) {
                return true
            } else {
                return false
            }
        }
    },
    async fetch() {
        this.docs = await this.$content(`ietm`).only(['slug', 'title', 'icon']).fetch() 
        this.dialogues = await this.$content(`dialogues`).only(['slug', 'title']).fetch() 
    }
}
</script>