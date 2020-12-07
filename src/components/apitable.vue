<template>
        <div>
    <h1 >Popis recepata</h1>
    <h3>Ova tablica je napravljena pomoću axios-a, uzima edamam-ov api za recepte na stranici.</h3>
    <table>
        <tr>
            <td>Ime jela (na engleskom)</td>
            <td>Slika jela</td>
            <td>Sastojci jela (na engleskom)</td>
            <td>Poveznica za puni recept</td>
        </tr>
        <tr v-for="item in list" v-bind:key="item.id">
            <td :id="'a'+item.recipe.yield+item.recipe.dietLabels[0]">{{item.recipe.label}}</td>
            <td><img :src="item.recipe.image"></td>
            <td>{{item.recipe.ingredientLines}}</td>
            <td><a :href="item.recipe.url">Poveznica</a></td>
        </tr>
    </table>
        </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios,axios)
export default {
    name: "RecipeList",
    data()
    {
        return {list:undefined}
    },
    mounted()
    {
        Vue.axios.get('https://api.edamam.com/search?q=main&app_id=0668221e&app_key=9c7c1b04cbabda98396715575c6223c2')
        .then((resp)=>{
            this.list=resp.data.hits;
            console.warn(resp.data.hits)
        })
    }
}
</script>

<style scoped>
h1{
   font-size: 72pt ;
}
h3{
    font-size:24pt;
}
tr{
    height:400px;
}
tr:first-of-type{
    height: auto;
}
td{
    margin:auto;
    height: 100%;
    padding:10% 0;
    text-align: center;
}
tr:first-of-type td{
    height: auto;
    padding: 0;
}
div{
  background-color:lightblue;
}
</style>
