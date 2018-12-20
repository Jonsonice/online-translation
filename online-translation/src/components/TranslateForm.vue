<template>
  <div id="translateForm">
	<form v-on:submit="formSubmit">
		<input type="text" placeholder="输入需要翻译的内容" v-model="textToTranslate">
		<select v-model="language">
			<option value="en">English</option>
			<option value="ru">Russian</option>
			<option value="ko">Korean</option>
			<option value="ja">Janpenese</option>
			
		</select>
		<input type="submit" value="翻译">
	</form>
  </div>
</template>

<script>

export default {
  name: 'translateForm',
  data:function(){
	return{
		textToTranslate:"",
		language:""
	}  
  },
  methods:{
	  formSubmit:function(e){
		  // alert(this.textToTranslate);
		  this.$emit("formSubmits",this.textToTranslate,this.language);
		  e.preventDefault();//取消默认事件 刷新页面
	  }
  }
}
</script>

<style>

</style>
