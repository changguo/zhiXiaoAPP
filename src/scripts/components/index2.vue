<template lang="html">
  <div class="box">
    <div class="index-container">
      <div class="yo-header yo-header-normal">
        <h2 class="title">{{title}}</h2>
        <span class="regret" v-on:click="forback">
            <i class="yo-ico">&#xf07d;</i>
            返回
        </span>
      </div>
      <div class="content">
        <router-view :transition="transitions"></router-view>
    </div>
  </div>
</template>

<script>
import VueRouter from '../libs/vue-router.js';
import Vue from '../libs/vue.js';
import VuexSet from '../vuex/actions.js';
import VuexGet from '../vuex/getters.js';
Vue.use(VueRouter);
export default {
  vuex: {
    actions:{
      loginPrePathShift: VuexSet.loginPrePathShift
    },
    getters:{
      getLoginPrePath: VuexGet.loginPrePath
    }
  },
  data () {
    return {
      title:'',
      transitions: 'goto'
    }
  },
  props: ['loginTitle'],
  methods: {
    forback(){
      this.transitions = 'back';
      var path = this.getLoginPrePath[0].path;
      this.loginPrePathShift();
      this.$router.go(path);
      setTimeout(()=>{
        this.transitions = 'goto';
      },500);
    }
  },
  computed:{
    title () {
      return this.getLoginPrePath[0].title
    }
  },
  ready(){
    this.title = this.$route.query.title;
  }
}
</script>
