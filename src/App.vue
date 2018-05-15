<template>
	<div id="app">
		<!--<img src="./assets/logo.png">-->
		<!--<router-view/>-->
		<div>
			
		</div>
		<VueUEditor ueditorPath="../../static/ueditor1_4_3_3/" @ready="editorReady"></VueUEditor>
	</div>
</template>

<script>
	import VueUEditor from 'vue-ueditor'
	export default {
	  name: 'app',
	  components: {
	    VueUEditor
	  },
		methods: {
			editorReady(editorInstance) {
				editorInstance.setContent('Hello world!<br>编辑初始化内容')
				editorInstance.addListener('contentChange',() =>{
					console.log('内容改变 ：',editorInstance.getContent())
				})
			}
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>