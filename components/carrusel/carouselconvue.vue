<template>
<div class="carousel col-lg-6 col-md-10 col-sm-12 col-xs-12 my-auto mx-auto">
    <input @click="paginationActive(index)" v-for="(image,index) of images" :key="index" type="radio" :id="index" name="image-slide" hidden>
    <div class="wrapper-slide-pagination">
        <div class="slide">
            <div  v-for="(image, index) in images"
            :key="image.id"
            :index="index"
            :visibleSlide="visibleSlide">
                <transition :name="direction" mode="in-out">
                    <div v-show="visibleSlide === index" class="slide-item col-12">
                        <img :src="'https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/' +image.large" alt="asd">
                    </div>
                </transition>
            </div>
            
            <button @click="prev" class="prev"><fa icon="chevron-left"></fa></button>
            <button @click="next" class="next"><fa icon="chevron-right"></fa></button>
        </div>
        <div class="carousel-pagination mx-3">
            <label  :class="['pagination-item','mx-1' , {activated:visibleSlide===index}]" v-for="(image,index) of images" :key="image.ide"  :for="index">
                <img  :src="`https://s3.sa-east-1.amazonaws.com/simplimotos-stg.com/${image.thumbnail}`">
            </label>
        </div>
    </div>
    <div class="row characteristics mx-auto">
            <div class="col-lg-4 col-md-4 col-sh-12 col-xs-12 my-2">- {{car.detail.characteristics.engine}}</div>
            <div class="col-lg-8 col-md-8 col-sh-12 col-xs-12 my-2">- {{car.detail.characteristics.warranty}}</div>
            <div class="col-lg-4 col-md-4 col-sh-12 col-xs-12 my-2">- {{car.detail.characteristics.gas_type}}</div>
            <div class="col-lg-8 col-md-8 col-sh-12 col-xs-12 my-2">- {{car.detail.characteristics.body}}</div>
    </div>
</div>
</template>

<script>
export default {
    props: ['images', 'car', 'visibleSlide','direction', 'paginatioValue'],
    methods: {
        next(){
            this.$emit('next')            
        },
        prev(){
            this.$emit('prev')
        },
        paginationActive(index){
            this.$emit('paginationActive', index)
        }
    }
}
</script>

<style>
@import '../../assets/carousel.css'
</style>