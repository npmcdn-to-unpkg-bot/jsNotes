<script src="https://unpkg.com/vue/dist/vue.js"></script>

<div id="app">
    {{ message }}
	<input v-model="message"/>
	<input type="button" v-on:click="get"/>
</div>

<script>
new Vue({
    el: '#app',
    data: {
        message: 'Hello Vue.js!'
    },
		methods: {
			get: function(){
				//this.message = "he"
				console.log('nihao')
				this.setMsg='wa'
				// this.setMsg
			}
		},
		computed: {
			getMsg:function() {
				return this.message
			},
			setMsg: {
				get: function(){
					//return this.message=this.message+"lala"
					return this.message+'1212'//没有结果
				},
				set: function(newmsg) {
					this.message = newmsg
				}
			}
		},
})
</script>