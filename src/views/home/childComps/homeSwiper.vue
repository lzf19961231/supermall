<template>
    <swiper>
        <swiperItem v-for="item in banners">
            <a :href="item.link">
                <img :src="item.image" alt="">
            </a>
        </swiperItem>
    </swiper>
</template>

<script>
    import {swiper, swiperItem} from 'components/common/swiper';

    export default {
        name: "homeSwiper",
        props:{
          banners:{
              type:Array,
              default(){
                  return []
              }
          }
        },
        components:{
            swiper,
            swiperItem
        }
    }

</script>

<style scoped>

</style>