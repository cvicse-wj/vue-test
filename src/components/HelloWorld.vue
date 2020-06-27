<template>
  <div class="hello">
	<button @click="flag=!flag">切换工程</button>
	<Task v-show="flag"></Task>
	<!-- <Message v-show="flag"></Message> -->
	<br />
	<User v-show="!flag"></User>
  </div>
</template>

<script>
//import Message from '@/components/pl/Message.vue'
import Task from '@/components/task/Task.vue'
import User from '@/components/user/User.vue'
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
	//Message,
	Task,
	User
  }
}
</script>

<style scoped>
	
</style>
