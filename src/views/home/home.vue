<template>
    <div id="home">
        <navBar class="home-nav">
            <div slot="center">购物街</div>
        </navBar>
        <homeSwiper :banners="banners"/>
        <recommendView :recommends="recommends"/>
    </div>
</template>

<script>
    import navBar from 'components/common/navBar/navBar';
    import homeSwiper from './childComps/homeSwiper';
    import recommendView from './childComps/recommendView'

    import {getHomeMultiData} from "network/home";


    export default {
        name: "home",
        components: {
            navBar,
            homeSwiper,
            recommendView
        },
        data() {
            return {
                banners: [],
                recommends: []
            }
        },
        created() {
            getHomeMultiData().then(res => {
                this.result = res;
                this.banners = res.data.banner.list;
                this.recommends = res.data.recommend.list;
                console.log(this.$data);
            });
        }
    }
</script>

<style scoped>
    .home-nav {
        background-color: var(--color-tint);
        color: #fff;
    }
</style>
