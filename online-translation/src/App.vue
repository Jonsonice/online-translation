<template>
  <div id="app">
		<h1>在线翻译</h1>
		<h5>简单 / 易用 / 便捷</h5>
		<translateForm v-on:formSubmits="translateText"></translateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'

export default {
  name: 'App',
  components: {
    TranslateForm
  },
	methods:{
		translateText:function(text){
			alert(text);
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
