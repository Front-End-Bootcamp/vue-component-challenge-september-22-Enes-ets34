<template>
	<ul class="list-group">
		<MembersListItem
			v-for="member in members"
			:key="member.id"
			:member="member"
		/>
	</ul>
</template>
<script setup>

import MembersListItem from "./MembersListItem.vue";

const props = defineProps({ members: Array });
</script>
