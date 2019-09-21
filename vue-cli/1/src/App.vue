<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
      <!-- <router-link to="/mine">我的</router-link> -->
      <!-- params传参 不能使用path直接传 需要使用name -->
      <router-link :to="{name:'mine',params:{id:444,name:'123'}}">我的params</router-link>
      <!-- query传参 -->
      <router-link :to="{path:'mine',query:{id:444,name:'123'}}">我的query</router-link>
      <!-- 通过路径传参 -->
      <router-link to="/test/2/lisi">test</router-link>
      <router-link to="/aaa">跳转</router-link>
      <router-link to="/c"></router-link>

      <button @click="$router.push('/')">首页</button>
      <button @click="$router.go(-1)"> 上一页 </button>
        <button @click="$router.go(1)"> 下一页 </button>>

    </div>
    <transition name="fade">
    <router-view/>
    </transition>
  </div>
</template>
<script>
      import CommomHeader from './components/CommonHeader';
      import CommomFooter from './components/CommonFooter';
      export default {
        components:{
          CommomHeader,
          CommomFooter
        },
        methods:{
          go(){
            this.$router.push('/');
          }
        }
}
</script>

<style lang="scss">

</style>
