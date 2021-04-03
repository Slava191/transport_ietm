<template>
<div>
    <nuxt-content :document="doc"/>
</div>
</template>

<style>
    table td, table th{
        border: solid 1px black;
        padding: 5px;
    }
</style>

<script>
export default {
    layout: 'docpage',
    async asyncData({ $content, params }){
        const doc = await $content(`ietm/${params.slug}`).fetch()
        const docs = await $content(`ietm`).only(['slug', 'title']).fetch()
        return { doc, docs }
    }
}
</script>