<template>
  <div class="hello">
	<button @click="flag=!flag">切换工程</button>
	<Message v-show="flag"></Message>
	<br />
	<Task v-show="!flag"></Task>
  </div>
</template>

<script>
import Message from '@/components/pl/Message.vue'
import Task from '@/components/task/Task.vue'
export default {
  name: 'HelloWorld',
  data(){
	return{
		flag:false
	}
  },
  props: {
  },
  components:{
	Message,
	Task
  }
}
</script>

<style scoped>
	button{
			margin-left: 8.25rem;
			width: 8.25rem;
			display: inline-block;
		}
</style>
