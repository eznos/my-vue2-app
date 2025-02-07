<template>

	<!-- Main Sidebar -->
	<a-layout-sider collapsible class="sider-primary" breakpoint="lg" collapsed-width="0" width="250px"
		:collapsed="sidebarCollapsed" @collapse="$emit('toggleSidebar', !sidebarCollapsed)" :trigger="null"
		:class="['ant-layout-sider-' + sidebarColor, 'ant-layout-sider-' + sidebarTheme]" theme="light"
		:style="{ backgroundColor: 'transparent', }">

		<div class="brand" :style="{ width: '100%', display: 'flex', alignItems: 'center', padding: 0 }">
			<img src="images/logo.png" alt="" style="margin-right: 10px;">
			<span>Komgrip Technologies</span>
		</div>
		<hr>

		<!-- Sidebar Navigation Menu -->
		<a-menu theme="light" mode="inline">
			<a-menu-item>
				<router-link to="/dashboard">
					<span class="icon">

						<svg width="20" height="20" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M3 1L0 4V5C0 5 2 6 4 6C6 6 8 5 8 5C8 5 10 6 12 6C14 6 16 5 16 5V4L13 1H3Z"
								fill="#000000" />
							<path fill-rule="evenodd" clip-rule="evenodd"
								d="M1 15V7.5187C1.81671 7.76457 2.88168 8 4 8C5.3025 8 6.51063 7.68064 7.38246 7.39737C7.60924 7.10177 7.81664 7.24612 8 7.17526C8.18337 7.24612 8.39076 7.10177 8.61754 7.39737C9.46737 7.68064 10.6975 8 12 8C13.1183 8 14.1833 7.76457 15 7.5187V15H7V10H4V15H1ZM12 10H10V13H12V10Z"
								fill="#000000" />
						</svg>
					</span>
					<span class="label">Dashboard</span>
				</router-link>
			</a-menu-item>
			<a-menu-item>
				<router-link to="/tables">
					<span class="icon">
						<svg width="10" height="10" xmlns="http://www.w3.org/2000/svg">
							<rect x="0" y="0" width="10" height="10" fill="gray" />
						</svg>
					</span>
					<span class="label">Menu 1</span>
				</router-link>
			</a-menu-item>
			<a-menu-item>
				<router-link to="/billing">
					<span class="icon">
						<svg width="10" height="10" xmlns="http://www.w3.org/2000/svg">
							<rect x="0" y="0" width="10" height="10" fill="gray" />
						</svg>
					</span>
					<span class="label">Menu 2</span>
				</router-link>
			</a-menu-item>
			<a-menu-item>
				<router-link to="/rtl">
					<span class="icon">
						<svg width="10" height="10" xmlns="http://www.w3.org/2000/svg">
							<rect x="0" y="0" width="10" height="10" fill="gray" />
						</svg>
					</span>
					<span class="label">Menu 3</span>
				</router-link>
			</a-menu-item>

			<a-menu-item>
				<router-link to="/rtl">
					<span class="icon">
						<svg width="10" height="10" xmlns="http://www.w3.org/2000/svg">
							<rect x="0" y="0" width="10" height="10" fill="gray" />
						</svg>
					</span>
					<span class="label">Menu 4</span>
				</router-link>
			</a-menu-item>

		</a-menu>
		<!-- / Sidebar Navigation Menu -->

		<!-- Sidebar Footer -->
		<div class="aside-footer">
			<div class="footer-box" :style="{
				backgroundColor: '#7D8799'
			}">

				<h6>Need Help?</h6>
				<p>CoinCap API 2.0</p>
				<a-button type="primary"
					href="https://demos.creative-tim.com/muse-vue-ant-design-dashboard/documentation" block
					target="_blank">
					DOCUMENTATION
				</a-button>
			</div>
		</div>
		<!-- / Sidebar Footer -->

	</a-layout-sider>
	<!-- / Main Sidebar -->

</template>

<script>

export default ({
	props: {
		// Sidebar collapsed status.
		sidebarCollapsed: {
			type: Boolean,
			default: false,
		},

		// Main sidebar color.
		sidebarColor: {
			type: String,
			default: "primary",
		},

		// Main sidebar theme : light, white, dark.
		sidebarTheme: {
			type: String,
			default: "light",
		},
	},
	data() {
		return {
			// sidebarCollapsedModel: this.sidebarCollapsed,
		}
	},
})

</script>
