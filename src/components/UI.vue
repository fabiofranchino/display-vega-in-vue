<template>
    <div class="ui">
        <h1>Paste a Vega share URL (copied from Vega-Editor)</h1>
        <input type="text" v-model="purl" placeholder="https://vega.github.io/editor/#/url/vega-lite/..." />
        <button @click="submit">Display!</button>
    </div>
</template>



<script>
export default {
    props:{
        url:String
    },
    data(){
        return{
            purl:''
        }
    },
    methods:{
        submit(){
            this.$emit('update:url', this.purl)
        }
    }
}
</script>



<style scoped>
.ui{
    padding: 2rem;
}
input{
    width: 100%;
    border: none;
    border: 1px solid #ddd;
    box-shadow: 0 0 10px #ccc;
    display: block;
}
</style>