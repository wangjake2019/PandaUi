<template>
	<div class="preview-container">
		<el-card shadow="hover" header="波浪指令效果（v-waves）作用于 btn">
			<el-row class="mb10" style="color: #808080">可选参数 v-waves=" |light|red|orange|purple|green|teal"</el-row>
			<div class="flex-warp">
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves>默认效果</el-button>
					</div>
				</div>
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button type="primary" size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves="'light'">light 效果</el-button>
					</div>
				</div>
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button type="success" size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves="'red'">red 效果</el-button>
					</div>
				</div>
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button type="info" size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves="'orange'">orange 效果</el-button>
					</div>
				</div>
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button type="warning" size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves="'purple'">purple 效果</el-button>
					</div>
				</div>
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button type="danger" size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves="'green'">green 效果</el-button>
					</div>
				</div>
				<div class="flex-warp-item">
					<div class="flex-warp-item-box">
						<el-button type="primary" size="small" icon="iconfont icon-bolangnengshiyanchang" v-waves="'teal'">teal 效果</el-button>
					</div>
				</div>
			</div>
		</el-card>
		<el-card shadow="hover" header="波浪指令效果（v-waves）作用于 div" class="mt15">
			<div class="waterfall-first">
				<div class="waterfall-first-item" v-for="v in 12" :key="v" v-waves>
					<div class="w100 h100 flex">
						<span class="flex-margin">{{ v }}</span>
					</div>
				</div>
			</div>
		</el-card>
	</div>
</template>

<script lang="ts">
import { toRefs, reactive } from 'vue';
export default {
	name: 'pagesWaves',
	setup() {
		const state = reactive({});
		return {
			...toRefs(state),
		};
	},
};
</script>

<style scoped lang="scss">
.preview-container {
	.flex-warp {
		display: flex;
		flex-wrap: wrap;
		align-content: flex-start;
		margin: 0 -5px;
		.flex-warp-item {
			padding: 5px;
			.flex-warp-item-box {
				width: 100%;
				height: 100%;
			}
		}
	}
	.waterfall-first {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(188px, 1fr));
		grid-gap: 0.25em;
		grid-auto-flow: row dense;
		grid-auto-rows: 20px;
		.waterfall-first-item {
			width: 100%;
			background: var(--color-primary);
			color: var(--color-whites);
			transition: all 0.3s ease;
			border-radius: 3px;
			&:nth-of-type(3n + 1) {
				grid-row: auto / span 5;
			}
			&:nth-of-type(3n + 2) {
				grid-row: auto / span 6;
			}
			&:nth-of-type(3n + 3) {
				grid-row: auto / span 8;
			}
			&:hover {
				box-shadow: 0 2px 12px 0 rgb(0 0 0 / 10%);
				transition: all 0.3s ease;
				cursor: pointer;
			}
		}
	}
}
</style>
