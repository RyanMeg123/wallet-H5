<template>
    <div class="share-container">
       <img :src="imgSrc" style="width:375px;height:667px;" v-if="imgSrc">
       <div class="share-card">
           <div class="lists">
               <div class="card-list">
                   <div class="list-img green">
                       <img src="../assets/icon-wx.png" class="img">
                   </div>
                   <div style="margin-top:15px;">{{$t('Home.wx')}}</div>
               </div>
               <div class="card-list">
                   <div class="list-img green">
                       <img src="../assets/icon-wxp.png" class="img">
                   </div>
                   <div style="margin-top:15px;">{{$t('Home.wxp')}}</div>
               </div>
               <div class="card-list" @click="picChange">
                   <div class="list-img purple">
                       <img src="../assets/icon-download.png" class="img">
                   </div>
                   <div style="margin-top:15px;">{{$t('pic.download')}}</div>
               </div>
               <div class="card-list">
                   <div class="list-img blue">
                       <img src="../assets/icon-twitter.png" class="img">
                   </div>
                   <div style="margin-top:15px;">{{$t('Home.twitter')}}</div>
               </div>
           </div>
           <div class="share-bottom" @click="cancelChange">{{$t('Home.cancel')}}</div>
       </div>
    </div>
</template>

<script>
export default {
  name: 'share',
  props: {
    imgSrc: String
  },
  methods: {
    cancelChange () {
      this.$emit('cancel')
    },
    //  生成美图
    picChange () {
      this.$emit('picChange')
    }
  }
}
</script>

<style scoped lang="less">
.share-container{
    display: flex;
    flex-direction: column;
    flex:auto;
    align-items: stretch;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index:999;
    .share-card{
        display: flex;
        flex-direction: column;
        height:240px;
        background:#fff;
        padding:50px 0 30px 0;
        position: absolute;
        width:100%;
        top:78.5%;
        left:0;
        .lists{
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            align-items: center;
            .card-list{
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                color:#7B7C81;
                font-size:24px;
                cursor: pointer;
                .list-img{
                    display: flex;
                    flex-direction: row;
                    justify-content: center;
                    align-items: center;
                    padding:26px;
                    width:60px;
                    height:60px;
                    border-radius: 50%;
                    .img{
                        width:60px;
                        height:60px;
                    }
                }
                .green{
                    background-color: #1DB01D;
                }
                .purple{
                    background-color: #4D51C6;
                }
                .blue{
                    background-color: #2B86F1;
                }
            }
        }
    }
    .share-bottom{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin-top:40px;
        font-size:24px;
        color:#7B7C81;
        font-weight: bold;
        cursor: pointer;
       }
}
</style>
