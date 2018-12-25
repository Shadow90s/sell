/*
 * @Author: 2273730450@qq.com 
 * @Date: 2018-12-18 10:09:59 
 * @Last Modified by: shadowRen
 * @Last Modified time: 2018-12-18 14:17:14
 */

<template>
  <div class="header">
    <div class="content-wrapper">
      <div class="avatar">
        <img width="64" height="64" :src="seller.avatar" alt="">
      </div>
      <div class="content">
        <div class="title">
          <img class="brand" src='brand@2x.png' />
          <span calss="name">{{seller.name}}</span>
        </div>
        <div class="description">
          {{seller.description}}/{{seller.deliverTime}}分钟送达
        </div>
        <div v-if='seller.supports' class='support'>
          <span class="icon"></span>  
          <span class="text">{{seller.supports[0].description}}</span>
        </div> 
      </div>
    </div>
    <div class="bulletin-wrapper"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
            
    }
  },
  props:['seller']
}

</script>
<style lang='scss'>
    .header{
      color: #fff;
      background: #000;
      .content-wrapper{
        padding: 24px 12px 18px 24px;
        font-size: 0;
        .avatar{
          vertical-align: top;
          display: inline-block;
          img{
            border-radius: 2px;
          }
        }
        .content{
          display: inline-block;
          margin-left: 16px;
          font-size: 14px;
          .title{
            margin: 2px 0 8px 0;
            .brand{
              vertical-align: top; 
              display: inline-block;
              width: 30px;
              height: 18px;
            }
            .name{
              line-height: 18px;
              margin-left: 6px;
              font-size: 16px;
              line-height: 18px;
              font-weight: blod;
            }
          }
          .description{
            margin-bottom: 10px;
            line-height: 12px;
            font-size: 12px;
          }
          .support{
            .icon{
              display: inline-block;
              width: 12px;
              height: 12px;
              margin-right: 4px;
            }
            
          }
        }
      }
    }
</style>