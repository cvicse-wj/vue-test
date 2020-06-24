<template>
	<li @mouseenter="handlerEnter(true)" @mouseleave="handlerEnter(false)" :style="{background : bgColor}">
		<label>
			<input type="checkbox" v-model="todo.todoFlag"/>
			<span>{{todo.todoName}}</span>
		</label>
		<button class="btn btn-danger" @click="deleteThis" v-show="showFlag">刪除</button>
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
					this.bgColor="#cccccc";
				}else{
					this.showFlag=false;
					this.bgColor="#ffffff";
				}
			}
		}
	}
</script>

<style scoped="scoped">
li {
    list-style: none;
    height: 36px;
    line-height: 36px;
    padding: 0 5px;
    border-bottom: 1px solid #ddd;
  }

li label {
float: left;
cursor: pointer;
}

li label li input {
vertical-align: middle;
margin-right: 6px;
position: relative;
top: -1px;
}

li button {
float: right;
margin-top: 3px;
}

li:before {
content: initial;
}

li:last-child {
border-bottom: none;
}
</style>
