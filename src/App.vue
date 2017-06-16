<template>
  <div>
    <div class="tab border-1px">
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

<script >
export default {
  
}
</script>

<style lang="scss" rel="stylesheet/scss">
.tab{ 
    width: 100%;
    height: 80px;
    line-height: 80px;
    border-bottom: 1px solid rgba(7, 17, 27, 0.1);
    display: flex;
    .tab-item{
      flex: 1;
      a{
        display: block;
        text-align: center;
        font-size: 14px;
      }
      a:hover{
        text-decoration: none;
        
      }
    }
}
</style>
