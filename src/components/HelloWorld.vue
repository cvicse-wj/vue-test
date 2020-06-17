<template>
  <div class="hello">
	<Message v-show="flag"></Message>
	<br />
	<button @click="flag=!flag">切换工程</button>
  </div>
</template>

<script>
import Message from '@/components/pl/Message.vue'
export default {
  name: 'HelloWorld',
  data(){
	return{
		flag:true
	}
  },
  props: {
  },
  components:{
	Message
  }
}
</script>

<style scoped>

</style>
