<template>
	<div id="app">
		<el-container>
			<el-header>
				<el-row :gutter="10" class="topnav">
					<el-col :xs="4" :sm="4" :md="4" :lg="4" :xl="4" class="topnav-l">
						<img class="topnav-img" src="../static/images/202006221019908124.png" />
					</el-col>
					<el-col :xs="10" :sm="10" :md="10" :lg="12" :xl="14">
						<el-menu class="el-menu-demo topnav" mode="horizontal" @select="handleSelect" background-color="#545c64"
						 text-color="#fff" active-text-color="#ffd04b">
							<el-menu-item index="/zd/zdIndex">制度门户</el-menu-item>
							<el-menu-item index="/house/houseIndex">会议室一览</el-menu-item>
							<el-menu-item index="/news/NewsIndex">信息门户</el-menu-item>
							<el-submenu index="2">
								<template slot="title">更多门户</template>
								<el-menu-item index="/Document/DocumentIndex">流程门户</el-menu-item>
								<el-menu-item index="/Gov/GovIndex">知识门户</el-menu-item>
								<el-menu-item index="/Hrm/HrIndex">人事门户</el-menu-item>
							</el-submenu>
							<el-menu-item index="4"><a href="https://www.ele.me" target="_blank">外部链接</a></el-menu-item>
						</el-menu>
					</el-col>
					<el-col :xs="10" :sm="9" :md="9" :lg="8" :xl="6" class="topnav-r">
						按钮
					</el-col>
				</el-row>
			</el-header>
			<el-container>
				<el-aside class="nav-aside"  >
					<el-menu
					      default-active="2"
					      class="el-menu-vertical-demo"
					      @open="handleOpen"
					      @close="handleClose"
					      background-color="#545c64"
					      text-color="#fff"
					      active-text-color="#ffd04b">
					      <el-submenu index="1">
					        <template slot="title">
					          <i class="el-icon-location"></i>
					          <span>导航一的</span>
					        </template>
					        <el-menu-item-group>
					          <template slot="title">分组一</template>
					          <el-menu-item index="/car/carindex1">选项1</el-menu-item>
					          <el-menu-item index="/car/carindex2">选项2</el-menu-item>
					        </el-menu-item-group>
					        <el-menu-item-group>
					          <template slot="title">分组二</template>
					          <el-menu-item index="/car/carindex1">选项1</el-menu-item>
					          <el-menu-item index="/car/carindex2">选项2</el-menu-item>
					        </el-menu-item-group>
					      </el-submenu>
						  
					      <el-menu-item index="2">
					        <i class="el-icon-menu"></i>
					        <span slot="title">导航二</span>
					      </el-menu-item>
					      <el-menu-item index="3" disabled>
					        <i class="el-icon-document"></i>
					        <span slot="title">导航三</span>
					      </el-menu-item>
					      <el-menu-item index="4">
					        <i class="el-icon-setting"></i>
					        <span slot="title">导航四</span>
					      </el-menu-item>
					    </el-menu>
				</el-aside>

				<el-main>
					<el-input v-model="input" placeholder="请输入内容"></el-input>
					<router-view></router-view>
				</el-main>
			</el-container>
			<el-footer style="background-color: #000088;">
				<div class="el-footer"></div>
			</el-footer>


		</el-container>
	</div>
</template>


<script>
	export default {
		data() {
			return {
				//activeIndex: '/news/NewsIndex'
			};
		},
		methods: {
			handleSelect(key, keyPath) {
				console.log(key, keyPath);
			}
		}
	}
</script>

<style lang="less" >
	@import '../static/css/public.css';
	.el-footer{height: 25px !important;}
	.topnav {
		background-color: #545c64;
		height: 60px;
		line-height: 60px;
		overflow: hidden;
	}
	.el-header{padding: 0 !important;}
	.el-submenu__title,
	.el-menu-item {
		height: 60px !important;
		line-height: 60px !important;
	}

	.topnav-l {
		padding-top: 10px;
		min-width: 240px;
	}

	.topnav-r {
		min-width: 320px;
	}

	.topnav-img {
		height: 45px;
		line-height: 45px;
	}
	.el-submenu .el-menu-item{min-width: inherit !important;padding: 0 !important;}
	.nav-aside{width: 160px !important;height: calc(100vh - 120px) ;background-color:#545c64;}
	html{font-size: 15px;} 
	
	.nav-aside li{padding: 0 10px !important;}
	.nav-aside li .el-submenu__title{padding-left: 0px !important;}
	.nav-aside .el-menu-item{height: 40px !important;line-height: 40px !important;}
</style>
