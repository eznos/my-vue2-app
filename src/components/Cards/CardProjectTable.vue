<template>

	<!-- Projects Table Card -->
	<a-card :bordered="false" class="header-solid h-full" :bodyStyle="{ padding: 0, }">
		<template #title>
			<a-row type="flex" align="middle">
				<a-col :span="24" :md="12">
					<h6>Crytocurrencies</h6>
					<!-- <p>done this month <span class="text-primary">+40%</span></p>	 -->
				</a-col>
				<a-col :span="24" :md="12" style="display: flex; align-items: center; justify-content: flex-end">
					<a-radio-group v-model="projectHeaderBtns" size="small">
						<a-button @click="handleClickBack" :style="{
							color: '#ec4899',
							border: '1px solid #ec4899',
							marginLeft: '10px'
						}">
							<svg fill="#ec4899" height="20px" width="20px" version="1.1" id="XMLID_287_"
								xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
								viewBox="0 0 24 24" xml:space="preserve">
								<g id="next" transform="scale(-1, 1) translate(-24, 0)">
									<g>
										<polygon points="6.8,23.7 5.4,22.3 15.7,12 5.4,1.7 6.8,0.3 18.5,12" />
									</g>
								</g>
							</svg>
						</a-button>
						<a-button @click="handleClickNext" :style="{
							color: '#ec4899',
							border: '1px solid #ec4899',
							marginLeft: '10px'
						}">

							<svg fill="#ec4899" height="20px" width="20px" version="1.1" id="XMLID_287_"
								xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
								viewBox="0 0 24 24" xml:space="preserve">
								<g id="next">
									<g>
										<polygon points="6.8,23.7 5.4,22.3 15.7,12 5.4,1.7 6.8,0.3 18.5,12 		" />
									</g>
								</g>
							</svg>

						</a-button>
					</a-radio-group>
				</a-col>
			</a-row>
		</template>
		<a-table :columns="columns" :data-source="data" :pagination="false">

			<template slot="rankx" slot-scope="rankx">
				<h6 class="m-0">

					{{ rankx.rank }}x
				</h6>
			</template>

			<template slot="company" slot-scope="company">
				<h6 class="m-0">
					<!-- <img :src="company.name" width="25" class="mr-10"> -->
					{{ company.name }}
				</h6>
			</template>

			<template slot="supply" slot-scope="record">
				<span>
					{{ parseFloat(record.supply).toFixed(2).toLocaleString() }} /
					{{ isNaN(parseFloat(record.maxSupply)) ? 'NO LIMIT' :
						parseFloat(record.maxSupply).toFixed(2).toLocaleString() || 'NO LIMIT' }}
				</span>
			</template>

			<template slot="priceUsd" slot-scope="priceUsd">
				<span>
					{{ '$ ' }}{{ parseFloat(priceUsd).toFixed(2) }}
				</span>
			</template>

			<template slot="changePercent24Hr" slot-scope="record">
				<span :style="{ color: parseFloat(record) >= 0 ? '#10b981' : '#ef4444' }">
					{{ record > 0 ? '+' : '' }}{{ parseFloat(record).toFixed(2) }}%
				</span>
			</template>
		</a-table>

	</a-card>


</template>

<script>



export default {
	props: {
		data: {
			type: Array,
			default: () => [],
		},
		columns: {
			type: Array,
			default: () => [],
		},
	},
	data() {
		return {
			projectHeaderBtns: 'all',
		}
	},

	computed: {
		changePercentStyle() {
			return (percent) => {
				return {
					color: percent >= 0 ? '#10b981' : '#ef4444'
				}
			}
		}
	},
	methods: {

		handleClickBack() {
			this.$emit('custom-event', -10);

		},
		handleClickNext() {
			this.$emit('custom-event', 10);
		}
	}
}

</script>