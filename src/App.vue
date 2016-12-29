<template>
  <div class="container">
    <menu-view></menu-view>
    <show-view :new-task="newTask"
               :doing="doing"></show-view>
    <div v-show="pageNewTask">


      <div class="container">
        <div class="row">
          <div class="col-xs-12">
          <div class="input-group">
            <span class="input-group-addon" id="sizing-addon2"><i class="fa fa-bookmark" aria-hidden="true"></i></span>
            <input type="text" class="form-control" placeholder="bookmark" aria-describedby="sizing-addon2" v-model="bookmark">
          </div>
        </div>
      </div>
      </div>

      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <iframe  class="renderHtml" :src="bookmark"></iframe>
          </div>
        </div>
      </div>

    </div>

    <div v-show="pageDoing">
      <!-- <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <iframe src="https://www.movie2free.com/page/3/"></iframe>
          </div>
        </div>
      </div> -->
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
      pageDoing: false,
      bookmark: ''
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

.renderHtml {
  width: 100%;
    height: 100vh;
    border: 10px solid white;
}


</style>
