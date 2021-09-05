<template>
    <div class="container-carousel col-lg-6 col-md-8 col-sm-12 col-xs-12">
        <input type="radio" id="0" name="image-slide" hidden>
        <input type="radio" id="1" name="image-slide" hidden>
        <input type="radio" id="2" name="image-slide" hidden>
        <input type="radio" id="3" name="image-slide" hidden>
        <div class="slide" >
            <div class="item-slide col-12" v-for="(image,index) of images" :key="index">
                <img :src="'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +image.large" name="image-slide">
            </div>
            
        </div>
        <div class="carousel-pagination col-lg-12">
            <label class="pagination-item" v-for="(image,index) of images" :key="index"  :for="index">
                <img :src="`https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/${image.thumbnail}`">
            </label>
        
        </div>
        <div class="row characteristics mx-auto">
            <div class="col-lg-4 col-md-4 col-sh-12 col-xs-12 my-2">- {{car.engine}}</div>
            <div class="col-lg-8 col-md-8 col-sh-12 col-xs-12 my-2">- {{car.warranty}}</div>
            <div class="col-lg-4 col-md-4 col-sh-12 col-xs-12 my-2">- {{car.gas_type}}</div>
            <div class="col-lg-8 col-md-8 col-sh-12 col-xs-12 my-2">- {{car.body}}</div>
        </div>
    </div>
    
</template>

<script>

export default {
    name: 'Carousel',
    props: ['car','images']
    
}
</script>
<style>
@import '../../assets/carousel.css';

.characteristics{
    display:flex;
    justify-content:space-between;
    text-align: left;
    font-size: 14px;
    color: #666;
}
@media screen and (max-width:720px) {
    .characteristics{
        flex-direction: column;
        margin-left:2%;
    }
}

</style>