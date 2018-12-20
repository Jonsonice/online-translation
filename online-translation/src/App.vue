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
			// alert(text);
			this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181220T142434Z.bd4bff0edd6e54be.564cbaddc02ba4ade4b1a35d33a70bc3099ea318&lang=en&text='+text)
			.then((response)=>{
				console.log(response.body.text[0]);
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
