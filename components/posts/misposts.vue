<template>
    <NuxtLink :to="'./posts/' + id" class="my-main-card-box col-lg-4 col-md-5 col-sm-10 col-xs-12 mx-auto py-2 px-1" >
        <div class="my-img-box">
            <img class="img-card" :src="`https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/${img}`" alt="imagen representativa del automovil">
        </div>
        <div class="px-3 py-3">
            <p class="model">{{model}}</p>

            <div class="price-box row ">
            <p class="col precio-desde">PRECIO DESDE</p>
            <p class="col price">${{precio}} USD</p>
            </div>

            <div class="view-detail d-flex justify-content-between view-detail col-lg-12 mb-3" >VER DETALLES DEL MODELO <fa class="right.arrow" icon="arrow-right" ></fa> </div>

            <p>{{name}}</p>
            <p class="descirption">
            Imágenes meramente ilustrativas no reportando la realidad exacta,
            pudiendo existir variaciones en la percepción.
            </p>

            <p></p>
        </div>
    </NuxtLink>
</template>
<script>
export default {
    name:"Cards",
    props:['precio', 'name', 'desc','img','model','id',],
    
}
</script>

<style>
.my-main-card-box{
    margin-top:1rem;
}
.my-main-card-box:hover{
    margin: 1px;
    cursor: pointer;
    border: solid rgba(150, 146, 146, 0.336) 1px;
    border-radius: 15px;
}
.img-card{
    max-width: 100%;
}
.model{
    text-align: center;
    font-weight:700;
    color: rgba(0, 0, 0, 0.658);
    font-size:26px;
    text-transform: uppercase;
}
.price-box{
    padding-top:10px;
    margin-bottom:10px;
    border-top: 0.5px solid rgba(128, 128, 128, 0.164);
    border-bottom: 0.5px solid rgba(128, 128, 128, 0.164);
}

.precio-desde{
    padding-top:4px ;
    font-weight: bolder;
    font-size: 13px;
    color:#c1c1c1;
}
.price{
    font-weight: bolder;
    font-size: 18px;
}
.view-detail{
    color: #c3002f;
    font-size:16px;
    font-weight:600;
}
.descirption{
    font-size:12.8px;
    color:#c1c1c1;
}
.right.arrow{
   align-content:end;
}
</style>