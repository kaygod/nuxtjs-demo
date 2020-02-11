<template>
  
  <div class="container">搜索页
  
     <div class="gap-top">
        <span class="gap" v-for="item of list">{{item.name}}</span>
     </div> 

  </div>


</template>
<script>

import dataSource from "~/static/data/search.json";

  
  export default {
    async asyncData ({ params }) {
     return { list: dataSource }
    },
    data(){
        return {
            list:[]
        }
    },  
    head () {
        return {
        title: "搜索"
        }
    }
  }

</script>
<style>
.gap-top{
    margin-top:20px;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  margin:0 auto;
  width:960px;
}
.gap{
    margin-left:10px;
}
</style>