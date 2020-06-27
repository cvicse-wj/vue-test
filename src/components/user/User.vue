<template>
	<div class="container">
		<UserHead></UserHead>
		<UserList ></UserList>
	</div>
</template>

<script>
import UserHead from '@/components/user/UserHead.vue'
import UserList from '@/components/user/UserList.vue'
export default{
	name:'User',
	data(){
		return{
			
		}
	},
	components:{
		UserHead,
		UserList
	},
	methods:{
		
	}
}
</script>

<style>
</style>
