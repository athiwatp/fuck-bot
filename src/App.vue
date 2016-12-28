<template>
  <div class="container">
    <menu-view></menu-view>
    <show-view :new-task="newTask"
               :doing="doing"></show-view>
    <div v-show="pageNewTask">
      <h1>newTask</h1>
    </div>

    <div v-show="pageDoing">
      <h1>Doing</h1>
    </div>

  </div>
</template>

<script>
import menuView from './components/menu'
import showView from './components/show'
export default {
  name: 'app',
  components: {
    menuView,
    showView
  },
  data () {
    return {
      keyword: '',
      pageNewTask: false,
      pageDoing: false
    }
  },
  methods: {
    newTask () {
      this.pageNewTask = true
      this.pageDoing = false
    },
    doing () {
      this.pageDoing = true
      this.pageNewTask = false
    }
  },
  mounted () {
    console.log(this.keyword)
  },
  computed: {
  }
}
</script>

<style>

@font-face {
   font-family: "San Francisco";
   font-weight: 200;
   src: url("https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-thin-webfont.woff");
}
body {
     animation: colorchange 50s;
     -webkit-animation: colorchange 50s;
     animation-iteration-count: infinite;
   }

   @keyframes colorchange
   {
     0%   {background: #3c375a;}
     25%  {background: #0191f7;}
     50%  {background: #ed1b72;}
     75%  {background: #f2d40d;}
     100% {background: black;}
   }

   @-webkit-keyframes colorchange
   {
     0%   {background: #3c375a;}
     25%  {background: #0191f7;}
     50%  {background: #ed1b72;}
     75%  {background: #f2d40d;}
     100% {background: black;}
   }

* {
  font-family: "San Francisco";
   color: white;
}



</style>
