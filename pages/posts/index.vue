<template>
    <div class="container d-flex cards-container" >
        <div v-if="show" class="row " >
            <Cards v-for="post of posts" 
                :key="post.id"
                :id="post.id"
                :precio="post.detail.price.amount"
                :desc="post.detail.main_description"
                :name="post.name"
                :img="post.detail.main_image.large"
                :model="post.model"
            />
        </div>
        <div v-else>dasasdasd</div>
        
    </div>
</template>

<script>
//cards genera mi pag que enlista los productos
import Cards from "../../components/posts/misposts"

export default {
    head(){
        return{
            title:"Nissan Store"
        }
    },
    //components va a tener los componentes que voy a utilizar
    components:{
        Cards
    },
    data() {
        return{
            posts: [],
            //show lo voy a utilizar para previsualizar una pantalla de carga mientras se generan los elementos
            show: false
        }
    },

    async created(){
    
        try {
            const {data} = await this.$axios.get('https://4my1q6hsyo.api.quickmocker.com/product')
            this.posts = data.results
            //una vez se cargan los elementos dedl api transformo show a true para quitar mi pantalla de carga y mostras mis elementos
            this.show = true
        
        } catch (error) {
            console.log(error)
        }

  }
}
</script>

<style>
@media screen and (min-width: 1147px){
    .cards-container{
        max-width: 80% !important;
    }
}
@media screen and (min-width: 576px) {
  footer {
    min-width: 100%;
  }
}
</style>
