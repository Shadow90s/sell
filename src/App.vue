/*
 * @Author: 2273730450@qq.com 
 * @Date: 2018-12-18 10:22:37 
 * @Last Modified by: shadowRen
 * @Last Modified time: 2018-12-18 19:10:52
 */
<template>
  <div id="app">
    <v-header :seller='seller'></v-header>
    <div class="tab">
      <div class="tab-item">
        <router-link to="/goods">商品</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/ratings">评论</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/seller">商家</router-link>
      </div>
      
    </div> 
    <router-view></router-view>
  </div>
</template>

<script>
  import header from 'components/header/header.vue';

  const ERR_OK = 0;

  export default {
    name: 'App',
    data() {
      return{
        seller:{}
      }
      
    },
    mounted() {
      this.$http.get('/api/seller').then((res)=>{
        if(res.body.errno === ERR_OK){
          this.seller = res.body.data;
        }
        
        console.log(res,'999999999999')
        console.log(this.seller,'res')
      })
    },
    components:{
      'v-header': header
    }
  }
</script>

<style lang="scss">
#app {
  .tab{
    display: flex;
    width: 100%;
    height: 40px;
    line-height: 40px;
    .tab-item{
      flex: 1;
      text-align: center;
      & > a{
        display: block;
        font-size: 14px;
        color: rgb(77,85,93);
        &.active{
          color: rgb(240,20,20)
        }
      }
    }
  }
}
</style>
