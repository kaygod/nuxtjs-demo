<template>
  
  <div class="container">详情页
  
     <ul class="gap-top">
            <li class="box" v-for="(value,key) of list">
                <p class="lt">{{key}}</p>
                <p class="gt">{{value}}</p>
            </li>
     </ul>
  
  </div>

</template>
<script>

import dataSource from "~/static/data/detail.json";  
  export default {
    async asyncData ({ params }) {
    return { list: dataSource }
  },
  data(){
    return {
      list:{}
    }
  },   
    head () {
        return {
        title: "详情"
        }
    }
  }

</script>
<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  margin:0 auto;
  width:960px;
}
.gap-top{
    margin-top:20px;
}
</style>