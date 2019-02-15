<template>
  <div id="app">
    <TabBar></TabBar>
  </div>
</template>

<script>
import TabBar from './components/tab/tabBar'
export default {
  name: 'App',
  created:function() {
    console.log('app created');
    this.$router.push('/');
  },
  components: {
    TabBar,
  },
}
</script>

<style>
#app {
  color: #2c3e50;
}
</style>


/*

    <img id="abc" src="./assets/logo.png">
    {{title}}
    <span>Message1:{{message}}</span>
    <!-- <p>LaLa: {{insertHtml}}</p> -->
    <!-- <div v-bind:id="dynamicId"></div> -->
    <!-- <span>Message2:{{methord1()}}</span> -->
    <!-- <p>LaLa: <span v-html="insertHtml"></span></p> -->

  data() {
    return {
      dynamicId:'id1',
      title:"NN",
      message:"大坏蛋",
      insertHtml:'<span style="color:red">I Love You!</span>',
    }
  },
  methods: {
      methord1:function() {
        console.log(this.dynamicId);
        return this.title + "test";
      }
  },
  create() {

  },
  mounted() {
   console.log(document.getElementById(this.dynamicId));
  }
  */