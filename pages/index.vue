<template>
	<div :id="attr.page">
		<button-template
			:template_type="'template_1'"
			:label_1="'Get Started'"
			:label_2="'Let\'s work together'"
			:min_width="200"
		 />

		 <br> <br>
		 <button-template
			:template_type="'template_1'"
			:template_type_secondary="'template_1_sec'"
			:label_1="'Schedule a Demo'"
			:label_2="'Start Now'"
			:min_width="200"
		 />
	</div>
</template>

<script type="text/javascript">
	export default {
		components: {
			ButtonTemplate: () => import ('~/components/templates/ButtonTemplate')
		}
	}
</script>

<style lang="stylus" module="attr">
	#page
		background-color: transparent
</style>