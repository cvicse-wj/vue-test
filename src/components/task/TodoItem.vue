<template>
	<li @mouseenter="handlerEnter(true)" @mouseleave="handlerEnter(false)" :style="{background : bgColor}">
		<label>
			<input type="checkbox" v-model="todo.todoFlag"/>
			<span>{{todo.todoName}}</span>
		</label>
		<button @click="deleteThis" v-show="showFlag">刪除</button>
	</li>
</template>

<script>
	export default{
		name:'TodoItem',
		data:function(){
			return{
				showFlag:false,
				bgColor:"white"
			}
		},
		props:{
			index:Number,
			todo:Object,
			deleteItem:Function
		},
		methods:{
			deleteThis:function(){
				if(window.confirm("是否要删除这个task？")){
					this.deleteItem(this.index)
				}
			},
			handlerEnter:function(value){
				if(value){
					this.showFlag=true;
					this.bgColor="aqua";
				}else{
					this.showFlag=false;
					this.bgColor="white";
				}
			}
		}
	}
</script>

<style scoped="scoped">
	input{
		width: 50px;
	}
	button{
		width: 3.125rem;
		margin-left: 3.125rem;
	}
	li{
		padding-top: 0.625rem;
		padding-bottom: 0.625rem;
		border: 1px solid aqua;
	}
</style>
