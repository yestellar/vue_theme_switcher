<template>
	<div class="header">
		<div class="logo">
			Theme Switcher
		</div>

		<label class="switcher">
			<input type="checkbox" v-model="isDarkTheme">
			<span class="slider round"></span>
		</label>
	</div>
</template>

<script>
export default {
	name: 'HeaderComponent',
	components: {
	},
	data: () => {
		return {
			isDarkTheme: localStorage.getItem('theme') === 'dark'
		}
	},
	watch: {
		isDarkTheme: {
			handler(val) {
				const theme = val ? 'dark' : 'light';
				document.documentElement.setAttribute('data-theme', theme);
				localStorage.setItem('theme', theme);
			},
			immediate: true
		}
	}
}
</script>

<style lang="sass" scoped>
@import "@/assets/sass/_variables.sass"

.header
	height: $header-height
	background: var(--color-background-primary)
	border-bottom: 1px solid var(--color-border)
	display: flex
	align-items: center
	padding: 0 15px

	.logo
		font-size: 20px
		font-weight: 600
		color: var(--color-text-primary)
		margin-right: 15px

	.switcher
		position: relative
		display: inline-block
		width: 44px
		height: 22px
		input
			opacity: 0
			width: 0
			height: 0
		.slider
			position: absolute
			cursor: pointer
			top: 0
			left: 0
			right: 0
			bottom: 0
			background-color: #d7d7d7
			transition: .3s
			&.round
				border-radius: 34px
				&:before
					position: absolute
					content: ""
					height: 16px
					width: 16px
					left: 4px
					bottom: 3px
					background-color: white
					transition: .3s
					border-radius: 50%
		input:checked + .slider
			background-color: var(--color-accent)
		input:checked + .slider:before
			transform: translateX(20px)
</style>