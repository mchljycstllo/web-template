<template>
	<div :class="[attr.button_container]">
		<nuxt-link
			:to="url"
			custom
			v-slot="{ href, navigate, isActive, isExactActive }"
			v-if="template_type == 'template_1'
		">
		<a
			:class="[
				(isExactActive) ? attr.exact : '',
				attr.button,
				attr[template_type],
				(template_type_secondary) ? attr[template_type_secondary] : '',
				attr.pointer,
				(disabled) ? attr.disabled : '',
				(minimal) ? attr.minimal : '',
				(full_width) ? attr.full : ''
			]"
			:style=" `min-width: ${min_width}px` "
			:href="href"
			@click="navigate"
		>
			<span :class="[attr.label, attr.label_1]">{{ label_1 }}</span>
			<span :class="[attr.label, attr.label_2]">{{ label_2 }}</span>
		</a>
		</nuxt-link>

		<a :href="`${url}`" v-else-if="template_type == 'template_2'"> {{ label }} </a>

	</div>
</template>

<script type="text/javascript">
	export default {
		props: {
			template_type: {
				type: String,
				default: 'template_1'
			},
			template_type_secondary: {
				type: String,
				default: ''
			},
			label_1: {
				type: String,
				default: 'Label 1'
			},
			label_2: {
				type: String,
				default: 'Label 2'
			},
			label: {
				type: String,
				default: 'Link'
			},
			url: {
				type: String,
				default: '/'
			},
			minimal: {
				type: String,
				default: ''
			},
			full_width: {
				type: String,
				default: ''
			},
			disabled: {
				type: Boolean,
				default: true
			},
			min_width: {
				type: Number,
				default: 200
			}
		}
	}
</script>

<style lang="stylus" module="attr">
	.button_container 
		.pointer
			cursor: pointer
		.template_1
			position: relative
			font-family: Roboto-Bold
			padding: 15px 20px
			display: inline-block
			text-align: center
			transition: .2s ease-out
			border: 1px solid var(--primary)
			border-radius: 10px
			&:before
				content: ""
				background-color: var(--primary)
				position: absolute 
				top: 0
				right: 0
				bottom: 0
				left: 0
				z-index: 1
				transition: .3s ease-out
				border-radius: 10px
			&.template_1_sec
				border: 1px solid var(--black)
				&:before 
					background-color: var(--white)
				.label
					color: var(--black)
				&:hover
					.label
						color: var(--white)
			.label 
				transition: .2s ease-out
				font-family: Roboto-Bold
				color: var(--white)
				position: relative 
				z-index: 2
				transition: .2s ease-out
				font-size: 18px
				&.label_1 
					display: block 
				&.label_2 
					display: none
			&:hover 
				border: 1px solid var(--black)
				background-color: var(--black)
				&:before 
					right: 100%
				.label_2
					display: unset
					transform: scale(2)
				.label_1 
					position: absolute
					right: 100%
			
</style>