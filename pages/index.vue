<template>
	<div :id="attr.page">
		<button-template
			:button_label="'Test button'"
			:classes="['hover', 'border_radius']"
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