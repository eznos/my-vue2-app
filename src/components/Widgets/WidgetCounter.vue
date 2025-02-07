<template>
	<a-card :bordered="false" class="widget-1">
		<a-statistic :title="title" :value="value" :prefix="prefix" :suffix="suffix" :precision="2" class="text-success"
			:class="'text-' + status">
			<template #suffix>
				<!-- เพิ่มคลาส suffix-block -->
				<span class="suffix-block">{{ suffix }}</span>
			</template>
		</a-statistic>
		<div class="icon" v-html="icon" :style="iconStyle"></div>
	</a-card>
</template>

<script>
export default {
	props: {
		title: {
			type: String,
			default: "",
		},
		value: {
			type: Number,
			default: 0,
		},
		prefix: {
			type: String,
			default: "",
		},
		suffix: {
			type: String,
			default: "",
		},
		icon: {
			type: String,
			default: "",
		},
		status: {
			type: String,
			default: "success",
		},
	},
	data() {
		return {}
	},
	computed: {
		iconStyle() {
			return {
				background: 'linear-gradient(to bottom right, #ec4899, #8b5cf6)',
				borderRadius: '16px',
				boxShadow: '0px 4px 10px rgba(0, 0, 0, 0.2)',
				width: '60px',
				height: '60px',
				display: 'flex',
				alignItems: 'center',
				justifyContent: 'center',
			}
		}
	}
}
</script>

<style scoped>
.suffix-block {
	display: block;
	margin-top: 5px;
}

.text-success .ant-statistic-suffix {
	white-space: nowrap;
	display: block;
	margin-top: 5px;
}
</style>