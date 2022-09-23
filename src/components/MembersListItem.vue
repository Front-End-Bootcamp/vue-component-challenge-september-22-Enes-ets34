<template>
	<li
		class="list-group-item"
		:class="{
			'bg-primary text-light': member.type === 'assistant',
		}"
	>
		{{ member.name }}
	</li>
</template>

<script setup>
const props = defineProps({ member: Object });
</script>

<style></style>
