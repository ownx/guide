<template>
	<div>
		<!-- user 页面 -->
		<router-link :to="'/user/' + item.id" key="index" v-for="item,index in userList"> {{item.userName}}</router-link>
		<div class="user-info" v-if="userInfo.userName">
			<p>姓名：{{userInfo.userName}} </p>
			<p>性别: {{userInfo.sex}}</p>
			<p>爱好: {{userInfo.hobby}}</p>
		</div>
	</div>
</template>

<script>
	let data = [{
			id: 1,
			tip: 'vip',
			userName: 'leo1',
			sex: '男',
			hobby: 'coding'
		},
		{
			id: 2,
			tip: 'vip',
			userName: 'stark',
			sex: '男',
			hobby: 'readbook'
		},
		{
			id: 3,
			tip: 'common',
			userName: 'xiaorong',
			sex: '男',
			hobby: '女'
		}
	]
	export default {
		data() {
			return {
				userList: data,
				userInfo: {}
			}
		},
		watch: {
			$route(){
				let id = this.$route.params.userId;
				console.log(this.$route)
				console.log(id)

				if(id){
					this.userInfo = this.userList.filter((item) => {
						return item.id == id
					})[0]
				}else{
					this.userInfo = {}
				}
			}
		},
		created() {
			// 渲染这个组件会调用一次这个生命周期函数
			// 复用这个组件，这个函数就不会再次调用了，
			let id = this.$route.params.userId;
			console.log(this.$route)
			console.log(id)

			if(id){
				this.userInfo = this.userList.filter((item) => {
					return item.id == id
				})[0]
			}else{
				this.userInfo = {}
			}
		}
	}
</script>

<style>
	
</style>