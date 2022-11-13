<template>
	<div id="app">
		<todo-app></todo-app>
	</div>
</template>

<script>

import TodoApp from './components/TodoApp.vue'
export default {
	name: "App",
		components: {
			TodoApp,
	},
};
</script>


<style lang="sass">
	// @use "sass:map"

	// $theme-colors: ("success": #28a745, "info": #17a2b8, "warning": #ffc107)

	// .alert
	// // Instead of $theme-color-#{warning}
	// background-color: map.get($theme-colors, "warning")

	$font-stack : -apple-system, BlinkMacSystemFont, avenir next, avenir, segoe ui, helvetica neue, helvetica, Cantarell, Ubuntu, roboto, noto, arial, sans-serif
    
	#app
		font-family: $font-stack
		-webkit-font-smoothing: antialiased
		-moz-osx-font-smoothing: grayscale
		text-align: center
		color: #2c3e50



</style>
