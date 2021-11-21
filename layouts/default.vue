<template>
  <div id="_web_template">
    <nav-bar />
    	<Nuxt />
    <Footer />
  </div>
</template>

<script type="text/javascript">
	import '~/assets/stylus/font.styl'
	import '~/assets/stylus/app.styl'
	export default {
		components: {
			NavBar: () => import('~/components/global/NavBar'),
			Footer: () => import('~/components/global/Footer'),
		},
		data: () => ({

		})
	}
</script>

<style lang="stylus">
	*
		margin: 0
		padding: 0
		box-sizing: border-box
</style>