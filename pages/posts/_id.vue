<template >
    <div v-if="show" class="contaienr-all">
        <div class="route-box row">
                <div class="col-lg-8 col-md-8 col-sh-8 col-xs-12 mx-3 route mx-auto">
                    <router-link class="back-to-store" to="/posts"><fa class="icon-arrow-left" icon="arrow-left"></fa> volver a la tienda </router-link>
                    <div class="mx-1 model-name"> / {{car.model}}</div>
                </div>
        </div>
        
        <div class="container">
            <div class="row">
                
                <Carousel
                :images="images"
                :car="car.detail.characteristics"
                />
                
                <div class="container-form my-3 py-2 col-lg-6">
                    <div class="h3">
                        INGRESÁ TUS DATOS
                    </div>
                    <div class="form-text">Por favor completá el siguiente formulario para que uno de nuestros asesores se pueda contactar contigo
                    </div>
                    <div class="form">
                        <div class="my-3 name row h-25 "><input class="form-input h-75" type="text" placeholder="NOMBRE Y APELLIDO"></div>
                        <div class="my-3 mail row h-25 "><input class="form-input h-75" type="mail" placeholder=" CORREO ELECTRONICO"></div>
                        <div class="my-3 phone row h-25 "><input class="form-input h-75" type="text" placeholder="TELEFONO"></div>
                        <div class="my-3 row"><button class="btn btn-danger send">ENVIARME LA COTIZACIÓN POR MAIL</button></div>   
                    </div>
                </div>
            </div>
        </div>
        
    </div>
    
    <div v-else>LOADING...</div>
</template>

<script>
import Carousel from '../../components/carrusel/carousel.vue';
export default {
  components: { Carousel},
    data() {
        return{
            car: [],
            images:[],
            //show lo voy a utilizar para previsualizar una pantalla de carga mientras se generan los elementos
            show: false
        }
    },
    async created(){
    
        try {
            const {data} = await this.$axios.get("https://4my1q6hsyo.api.quickmocker.com/product/" + this.$route.params.id)
            this.car = data
            this.images = data.gallery
            //una vez se cargan los elementos dedl api transformo show a true para quitar mi pantalla de carga y mostras mis elementos
            this.show = true
            console.log(this.car)
        
        } catch (error) {
            console.log(error)
        }

    }
}
/**/
</script>

<style>
.contaienr-all{
    height: 1000px;
}
.route-box{
    height: 70px;
    background-color: #ccc;
    width:100%;
    margin: 0;
}
.route{
    display: flex;
    justify-content: left;
    flex-wrap:wrap;
    font-size: 17px;
    align-items: center;
    font-family:'Times New Roman', Times, serif ;

}
.back-to-store{
    color: #c3002f;
    font-weight:400;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}
.back-to-store:hover{
    color: #d10232;
}
.icon-arrow-left{
    width:26px !important;
}
.send{
    background-color:#c3002f;
}
.container-form{
    
    border-top: 1px solid #e3e2e2;
}
.form{
    height: 100%;
    max-height: 200px;
}
.form-input{
    border: solid rgba(201, 201, 201, 0.568) 1px ;
    border-radius:9px;
}
.form-text{
    font-size: 16px;
    color: #b5b5b5;
}

</style>


