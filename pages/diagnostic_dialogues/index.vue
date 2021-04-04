<template>
    <div>

        <h1>Устранение неисправностей</h1>

        <ul class="section-items list-unstyled nav flex-column pb-3">
            <li class="nav-item section-title" v-for="item in dialogues" :key="item.slug" >
                <NuxtLink :to="`/diagnostic_dialogues/${item.slug}`" class="nav-link scrollto active">
                    <span class="theme-icon-holder mr-2"><i :class="item.icon"></i></span>{{item.title}}
                </NuxtLink>  
            </li>
        </ul>
        
    </div>
</template>

<script>
export default {
    layout: 'docpage',
    async asyncData({ $content }){
        const dialogues = await $content(`dialogues`).only(['slug', 'title', 'icon']).fetch() 
        return { dialogues }
    }
}
</script>