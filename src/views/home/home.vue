<template>
    <div id="home">
        <navBar class="home-nav">
            <div slot="center">购物街</div>
        </navBar>
        <homeSwiper :banners="banners"/>
        <recommendView :recommends="recommends"/>
        <featureView/>
        <tabControl class="tab-control" :titles="['流行','新款','精选']"/>

        <ul>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
            <li>玩狗一百下</li>
        </ul>

    </div>
</template>

<script>
    import navBar from 'components/common/navBar/navBar';
    import tabControl from 'components/content/tabControl/tabControl';

    import homeSwiper from './childComps/homeSwiper';
    import recommendView from './childComps/recommendView';
    import featureView from './childComps/featureView';

    import {
        getHomeMultiData,
        getHomeGoods
    } from "network/home";


    export default {
        name: "home",
        components: {
            homeSwiper,
            recommendView,
            featureView,
            navBar,
            tabControl
        },
        data() {
            return {
                banners: [],
                recommends: [],
                goods:{
                    "pop":{page:0,list:[]},
                    "new":{page:0,list:[]},
                    "sell":{page:0,list:[]}
                }
            }
        },
        created() {
            this.getHomeMultiData();
            this.getHomeGoods('pop');
            this.getHomeGoods('new');
            this.getHomeGoods('sell');
        },
        methods:{
            getHomeMultiData(){
                getHomeMultiData().then(res => {
                    this.banners = res.data.banner.list;
                    this.recommends = res.data.recommend.list;
                });
            },
            getHomeGoods(type){
                const page=this.goods[type].page+1;
                getHomeGoods(type,page).then(res=>{
                    this.goods[type].list.push(res.data.list);
                    this.goods[type].page+=1;
                });
            }
        }
    }
</script>

<style scoped>
    #home{
        padding-top: 44px;
    }
    .home-nav {
        background-color: var(--color-tint);
        color: #fff;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        z-index: 9;
    }
    .tab-control{
        position: sticky;
        top:44px;
    }
</style>
