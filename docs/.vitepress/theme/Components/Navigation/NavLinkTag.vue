<template>
	<span v-if="valid" :class="`${colour} label`">{{ title }}</span>
</template>

<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{
	tag: string
}>()

let valid = true
let title = ''
let colour = ''

switch (props.tag) {
	case 'guide': {
		title = 'GUIDE'
		colour = 'green'
		break
	}
	case 'exp':
	case 'experimental': {
		title = 'EXP'
		colour = 'orange'
		break
	}
	case 'beta': {
		title = 'BETA'
		colour = 'red'
		break
	}
	case 'help': {
		title = 'HELP'
		colour = 'blue'
		break
	}
	default:
		valid = false
		break
}
</script>
