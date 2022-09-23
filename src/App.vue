<script setup>
import data from "../data.json";
import { ref } from "@vue/reactivity";
import Header from "./components/Header.vue";
import Select from "./components/Select.vue";
import MembersList from "./components/MembersList.vue";

let members = ref(data);
let selectedGroup = ref("");

let groups = [
	...new Set(
		members.value.map((i) => {
			return i.group;
		})
	),
];
const selectGroup = (event) => {
	selectedGroup.value = event;
	console.log("event :>> ", event);
	members.value = members.value.filter((i) => i.group === selectedGroup.value);
};


</script>

<template>
	<Header />
	<div class="container mt-5">
		<div class="row">
			<div class="col-md-6 mx-auto">
				<div class="card mx-auto">
					<div class="card-header text-center">
						<h4>{{ selectedGroup }}</h4>
					</div>
					<div class="card-body">
						<Select @selectGroup="selectGroup($event)" :groups="groups" />
					</div>
					<div class="card-body">
						<MembersList :members="members" />
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped></style>
