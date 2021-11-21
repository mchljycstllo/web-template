<template>
  <div id="_web_template">
    <nav-bar />
    	<Nuxt />
    <Footer />
  </div>
</template>

<script type="text/javascript">
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
	#_web_template
		background-color: transparent
</style>