<template>
  <header-component/>
  <router-view/>
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
	HeaderComponent
  }
}
</script>

<style lang="sass">
*
	margin: 0
	padding: 0
	box-sizing: border-box
	outline: none

#app
	font-family: Avenir, Helvetica, Arial, sans-serif
	-webkit-font-smoothing: antialiased
	-moz-osx-font-smoothing: grayscale
	text-align: center
	color: #2c3e50
	height: 100vh
</style>
