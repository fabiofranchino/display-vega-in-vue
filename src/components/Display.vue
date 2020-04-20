<template>
    <div class="wrap">
        <div id="viz"></div>
    </div>
</template>



<script>
import LZString from 'lz-string'
import Embed from 'vega-embed'

export default {
    props:{
        url:String
    },
    
    async mounted(){
        let frag = this.url.replace('https://vega.github.io/editor/#/url/vega-lite/', '')
        let spec = LZString.decompressFromEncodedURIComponent(frag)
        let ob = JSON.parse(spec)
        ob.width = 'container'
        ob.height = 'container'
        await Embed('#viz', ob, {actions:false})
    }
}
</script>



<style scoped>
.wrap{
    width: 100%;
    height: 100%;
    padding: 1rem;
}
#viz{
    width: 100%;
    height: 100%;
}
</style>