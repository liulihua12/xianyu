<template>
    <div>
        <div class="vdo-title">
            <p title="减肥食谱一日三餐如何安排？">减肥食谱一日三餐如何安排？</p>
            <span>517082人看了这个视频</span>
        </div>
        <div class="vdo-div">
            <div class="vdo-vdo">
                <video id="v1" :src="src" loop muted autoplay controls width="500" height="300"></video>
                <span>17条相关视频</span>
                <div class="vdo-ul">
                    <ul v-for="(item,i) of list" ref="ul" :key="i">
                        <li class="vdo-li" @click="play(item.src)" :src="item.src">
                            <div>
                                <div class="vdo-img">
                                    <img :src="item.img" alt="">
                                </div>
                                <img src="../../assets/play_list_icon.png" alt="">
                            </div>
                            <div class="vdo-p-div">
                                <p>{{item.title}}</p>
                                <div class="vdo-p-img">
                                    <p></p>
                                    <span>{{item.span}}</span>
                                </div>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
            <ul class="ul-img">
                <li><img src="../../assets/1.jpg" alt=""><span>1</span></li>
                <li><img src="../../assets/2.jpg" alt=""><span>2</span></li>
                <li><img src="../../assets/3.jpg" alt=""><span>3</span></li>
                <li><img src="../../assets/4.jpg" alt=""><span>4</span></li>
            </ul>
        </div>
    </div>
</template>
<script>
    export default {
        data(){
            return {
                src:"video-0.mp4",
                list:[
                    {vid:1,img:"./img/video-2.jpg",src:"video-0.mp4",title:"一日三餐减肥食谱",span:"百姓健康网"},
                    {vid:2,img:"./img/video-1.png",src:"video-1.mp4",title:"二日三餐减肥食谱",span:"百姓健康网"},
                    {vid:3,img:"./img/video-2.jpg",src:"video-0.mp4",title:"三日三餐减肥食谱",span:"百姓健康网"},
                    {vid:4,img:"./img/video-1.png",src:"video-1.mp4",title:"四日三餐减肥食谱",span:"百姓健康网"},
                    {vid:5,img:"./img/video-2.jpg",src:"video-0.mp4",title:"五日三餐减肥食谱",span:"百姓健康网"}
                ]
            }
        },
        methods:{
            play(src){
                this.src=src;
            }
        }
    }
</script>

<style>
    h1,p,ul,li{
        margin:0;
        padding:0;
        list-style:none;
    }
    .vdo-title{
        width:1210px;
        height:80px;
        margin:10px auto;
        text-align:left;
    }
    .vdo-title>p{
        color:#333;
        font-size:28px;
        font-family: "Microsoft YaHei";
    }
    .vdo-div{
        display:flex;
        justify-content:space-around;
        width:1220px;
        margin:0 auto;
    }
    #v1{
        text-align:left;
    }
    .ul-img{
        display:flex;
        justify-content:space-around;
        flex-wrap:wrap;
        width:405px;
        height:312px;
        border:3px solid deeppink;
        background-color:deeppink;
        padding-top:1px;
    }
    .ul-img>li{
        width:200px;
        height:154px;
        overflow:hidden;
        position:relative;
    }
    .ul-img img{
        width:200px;
        height:154px;
        transition:0.2s;
    }
    .ul-img span{
        position:absolute;
        left:0;
        top:125px;
        width:30px;
        height:30px;
        text-align:center;
        line-height:30px;
        color:#fff;
        font-size:20px;
        background-color:rgba(61, 59, 59,0.6);
    }
    .ul-img img:hover{
        transform:scale(1.5);
    }
    .vdo-vdo{
        width:750px;
        display:flex;
        height:320px;
        align-items:center;
        background-color:#66666E;
        padding-left:20px;
        position:relative;
    }
    .vdo-vdo>span{
        position:absolute;
        top:20px;
        left:540px;
        color:ghostwhite;
    }
    .vdo-li{
        display:flex;
        width:219px;
        height:55px;
        padding-left:24px;
        padding-top:13px;
        padding-bottom:13px;
        position:relative;
    }
    .vdo-img{
        width:96px;
        height:54px;
    }
    .vdo-img>img{
        width:96px;
        height:54px;
    }
    .vdo-li>div>img{
        width:30px;
        height:30px;
        opacity:0.9;
        position:absolute;
        left:60px;
        top:25px;
    }
    .vdo-ul{
        margin-top:25px;
        height:255px;
        text-align:left;
        color:ghostwhite;
        cursor:pointer;
        overflow-x: hidden;
        overflow-y: auto;
    }
    /* 滚动条样式 */
    .vdo-ul::-webkit-scrollbar{
        width: 6px;     /*高宽分别对应横竖滚动条的尺寸*/
        height: 4px;
    }
    .vdo-ul::-webkit-scrollbar-thumb {/*滚动条里面小方块*/
        border-radius: 5px;
        -webkit-box-shadow: inset 0 0 5px rgba(0,0,0,0.2);
        background: rgba(0,0,0,0.2);
    }
    .vdo-ul::-webkit-scrollbar-track {/*滚动条里面轨道*/
        -webkit-box-shadow: inset 0 0 5px rgba(0,0,0,0.2);
        border-radius: 0;
        background: rgba(0,0,0,0.1);
    }
    .vdo-ul>span{
        position:absolute;
        top:0px;
        left:20px;
    }
    .vdo-p-img{
        display:flex;
        align-items:center;
        padding-left:15px;
        height:20px;
        color:#A1A1A3;
    }
    .vdo-p-img p{
        width:18px;
        height:18px;
        background:url("../../assets/video-sm.png") no-repeat center;
        background-size:contain;
        border-radius:50%;
    }
    .vdo-p-div{
        width:120px;
        font-size:12px;
    }
    .vdo-p-div>p{
        padding-left:15px;
        height:35px;
    }

</style>