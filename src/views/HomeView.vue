<template>
  <div class="home">
	<form class="form" @submit.prevent="auth">
		<h2 class="header">Sign in</h2>

		<div class="input-container">
			<label class="label" for="login">Login</label>
			<input class="input" type="text" id="login" name="login" required>
		</div>
		<div class="input-container">
			<label class="label" for="password">Password</label>
			<input class="input" type="password" id="password" name="password" required>
		</div>
		<button class="submit" type="submit">Submit</button>
	</form>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  components: {
  },
  methods: {
	auth() {
		const login = document.getElementById('login').value;
		const password = document.getElementById('password').value;

		console.log({ login, password });
	}
  }
}
</script>

<style lang="sass" scoped>
@import "@/assets/sass/_variables.sass"

.home
	height: calc(100% - #{$header-height})
	background: var(--color-background-secondary)
	display: flex
	justify-content: center
	align-items: center

	.form
		padding: 35px
		background: var(--color-background-primary)
		border-radius: 4px
		width: 400px
		.header
			font-size: 24px
			font-weight: 600
			color: var(--color-text-primary)
			margin-bottom: 20px

		.input-container
			display: flex
			flex-direction: column
			align-items: flex-start
			margin-bottom: 20px
			.label
				font-size: 14px
				font-weight: 400
				color: var(--color-text-primary)
				margin-bottom: 5px
			.input
				width: 100%
				padding: 10px 14px
				font-size: 14px
				font-weight: 400
				background: transparent
				border: 1px solid var(--color-border)
				border-radius: 4px
				color: var(--color-text-primary)
				transition: all .2s ease
				&:focus,
				&:hover
					border-color: var(--color-primary)
					outline: none
		.submit
			background: var(--color-accent)
			color: #fff
			border: none
			border-radius: 4px
			padding: 10px 14px
			width: 100%
			font-size: 14px
			font-weight: 500
			cursor: pointer
			transition: all .2s ease
			&:hover
				background: var(--color-accent-hover)
				color: #fff
				outline: none
</style>
