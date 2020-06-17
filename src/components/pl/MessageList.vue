<template>
	<div style="margin-top: 50px;">
		<h2 style="margin-bottom: 1.25rem;">评论回复：</h2>
		<h3 v-show="commentList.length===0">请添加评论</h3>
		<ul>
			<MessageItem v-for="(comment,index) in commentList" :comment="comment" :key="index" :deleteCommet='deleteCommet' :index="index"></MessageItem>
		</ul>
	</div>
</template>

<script>
import MessageItem from '@/components/pl/MessageItem.vue'

export default{
	name:'MessageList',
	props:{
		commentList:Array,
		deleteCommet:Function
	},
	data(){
		return{
			
		}
	},
	components:{
		MessageItem
	}
}
</script>

<style>
</style>
