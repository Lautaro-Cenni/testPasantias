<template>
  <div id="app" class="container contenedor">
    <div class="description row">
      <div class="col-12 ">
        <p class="description-index-main">AHORA ES ONLINE</p>
        <p class="description-index">Con Nissan Store, podés acceder a tu nuevo 0km con todos los servicios asociados desde la comodidad de tu sofá. Probanos!</p>
        </div>
         <router-link class="row button-container" to="./posts"><button  class=" col-lg-4 col-md-8 col-sm-11 col-xs-12 mx-auto btn btn-lg botton-index-description">Inicia tu experiencia <fa class="icono-flecha" icon="location-arrow" /></button></router-link>
    </div>
  </div>
</template>

<script>
export default {
  head(){
    return{
      title: 'Aplicacion de nuxt | Index',
      meta: [
        {
          name: "description",
          content: "webSite TestPasantias"
        }
      ],
      htmlAttrs:{
        lang:'en'
      }
    }
  }
  
}
</script>

<style>
a{
  text-decoration: none;
  color:black;
}
a:hover{
  color:black;
}
.contenedor{
  margin: 0;
  padding: 0;
  width:100% !important;
  height:800px;
  background-image: url("./static/Banner.jpg");
  background-size: 100% 100%;
}
.description{
  margin:0;
  width:100%;
  height:300px;
  background-color: rgba(61, 51, 51, 0.527);
  top:50%;
  position:absolute;
}
.description-index-main{
  text-align: center;
  font-size: 50px;
  font-weight: 600;
  color: rgb(231, 215, 213);
}
.description-index{
  text-align: center;
  font-size: 30px;
  font-weight: 500;
  color: rgb(231, 215, 213);

}
.icono-flecha{
  color: white;
  margin-left:1rem;
}
.botton-index-description {
  height: 4rem;
  background-color:#be0909ea ;
  border-color:#d81616;
  color: rgb(252, 248, 244);
}
.botton-index-description:hover{
  background-color:#db1d1d ;
  border-color:#ffb8b8;
  
  color: rgb(252, 248, 244);
}
.button-container{
  margin-left:0;
}



@media screen and (min-width: 576px) {
  .contenedor {
    min-width: 100%;
  }
}
@media screen and (max-width: 688px) {
  .description {
    top:260px;
    height: 520px;
    min-width: 100%;
  }
  .contenedor{
    background-size: auto 100%;
    background-repeat: no-repeat;
  }
}
@media screen and (max-width: 291px ){
  .botton-index-description{
    font-size: 17px ;
    
  }
  .icono-flecha{
    margin-left:1px;
  }
}

/* IMPORTANTE ESTE ESTILO APLICA PARA TODAS LAS PAGINAS */
@media screen and (min-width: 576px) {
  .contenedor {
    min-width: 100%;
  }
}
</style>
