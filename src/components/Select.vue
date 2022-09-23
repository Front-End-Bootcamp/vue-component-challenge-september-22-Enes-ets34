<template>
	<select
		@change="selectGroup($event)"
		class="form-select"
		aria-label="Default select example"
	>
		<option v-for="group in groups" :key="group">
			{{ group }}
		</option>
	</select>
</template>
<script setup>
const emit = defineEmits(["selectGroup"], selectGroup);
const selectGroup = (event) => {
	return emit("selectGroup", event.target.value);
};

const props = defineProps({ groups: Array });
</script>
