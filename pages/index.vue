<template>
  <div class="container">
        <nuxt-link to="/search">搜索页</nuxt-link>
        <nuxt-link to="/detail" v-bind:style="{ marginLeft: '20px' }">详情页</nuxt-link>
        <div><Logo/></div>
        <div>{{content}}</div>
        <ul>
            <li class="box" v-for="item in list">
                <p class="lt">{{item.name}}:</p>
                <p class="gt">{{item.price}}</p>
            </li>
        </ul>
        <Test/>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue';
import { getName } from "~/util/global.js";
import axios from "axios";
import dataSource from "~/static/data/index.json";
import Test from "~/container/index/test.vue";

export default {
  async asyncData ({ params }) {
    //let data  = await axios.get("/data/index.json")
    return { list: dataSource }
  },
  data(){
    return {
      content:"",
      list:[]
    }
  },
  mounted(){
    this.content = getName();
  },
  components: {
    Logo,
    Test
  },
   head () {
    return {
      title: "首页"
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

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
