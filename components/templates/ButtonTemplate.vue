<template>
	<div :class="[attr.button_container, attr[classes]]">
		<button :class="attr[classes]"> {{button_label}} </button>
	</div>
</template>

<script type="text/javascript">
	export default {
		props: {
			button_label: {
				type: String,
				default: 'Button'
			},
			classes: {
				type: Array,
				default: []
			}

		}
	}
</script>

<style lang="stylus" module="attr">
	.button_container 
		display: contents
		button 
			border-radius: 15px
			&:hover 
				cursor: pointer
			&.border_radius
				color: red
		
</style>