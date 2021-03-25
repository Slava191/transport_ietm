<template>
    <div class="container">
        <b-container class="bv-example-row">
            <b-row>
                <b-col sm="3">
                    <b-list-group>
                        <b-list-group-item 
                            v-for="item in docs" 
                            :key="item.slug" 
                            :to="`./${item.slug}`" 
                            :active="item.slug===doc.slug"
                        >
                            {{item.title}}
                        </b-list-group-item>
                    </b-list-group>
                </b-col>
                <b-col sm="9"><nuxt-content :document="doc"/></b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }){
        const doc = await $content(`ietm/${params.slug}`).fetch()
        const docs = await $content(`ietm`).only(['slug', 'title']).fetch()
        return { doc, docs }
    }
}
</script>