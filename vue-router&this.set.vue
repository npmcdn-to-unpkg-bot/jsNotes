<script src="https://unpkg.com/vue/dist/vue.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue-router/0.7.10/vue-router.min.js"></script>
<div id="app">
  <h1>Hello App!</h1>
  <p>
    <!-- use v-link directive for navigation. -->
    <a v-link="{ path: '/foo' }">Go to Foo</a>
    <a v-link="{ path: '/bar' }">Go to Bar</a>
  </p>
  <!-- use router-view element as route outlet -->
  <router-view></router-view>
</div>

<script>
	var Foo = Vue.extend({
    template: '<p>This is {{msg}}</p><input type="button" v-on:click="change" >',
    data: function(){
      return {
         msg:'he'
      }	
    },
    methods: {
    	change: function(){
      	//console.log(this.msg) work! he
        this.msg='wakaka'
      }
    }
})


var Bar = Vue.extend({
    template: '<p>This is bar!</p>'
})

var App = Vue.extend({})

var router = new VueRouter()

router.map({
    '/foo': {
        component: Foo
    },
    '/bar': {
        component: Bar
    }
})
router.start(App, '#app')

</script>