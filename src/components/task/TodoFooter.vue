<template>
	<div class="todo-footer">
		<input type="checkbox" v-model="checkAll"/>
		<span>已完成{{selectNum}}/全部{{allNum}}</span>
		<button class="btn btn-danger" @click="deleteSelect" v-show="selectNum>0">清除已完成的任务</button>
	</div>
</template>

<script>
	export default{
		name:"TodoFooter",
		data(){
			return{
				allNum:this.todos.length
			}
		},
		props:{
			todos:Array,
			deleteSelItem:Function
		},
		methods:{
			deleteSelect(){
				if(window.confirm("是否要删除所选中的任务列表？")){
					this.deleteSelItem()
				}
			}
		},
		computed:{
			checkAll:{
				get:function(){
					return this.allNum===this.selectNum && this.selectNum>0
				},
				set:function(){
					
				}
			},
			selectNum:function(){
				const array=this.todos.filter(t => t.todoFlag===true);
				return array.length;
			}
		}
	}
</script>

<style scoped="scoped">
  .todo-footer {
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
    margin-top: 5px;
  }

  .todo-footer label {
    display: inline-block;
    margin-right: 20px;
    cursor: pointer;
  }

  .todo-footer label input {
    position: relative;
    top: -1px;
    vertical-align: middle;
    margin-right: 5px;
  }

  .todo-footer button {
    float: right;
    margin-top: 5px;
  }
</style>
