<script setup lang="ts">
import { ref } from "vue";
import AppSelect from "./AppSelect.vue";
defineProps<{ msg: string }>();

const formState = ref({
	value: undefined,
	value2: undefined
});
</script>

<template>
	<a-button type="primary">Primary Button</a-button>
	<a-form :model="formState">
		<a-form-item label="选项1" name="value">
			<app-select v-model:value="formState.value" />
		</a-form-item>
		<a-form-item label="选项2" name="value2">
			<app-select v-model:value="formState.value2" />
		</a-form-item>
	</a-form>
	{{ formState.value }}
</template>

<style scoped>
a {
	color: #42b983;
}

label {
	margin: 0 0.5em;
	font-weight: bold;
}

code {
	background-color: #eee;
	padding: 2px 4px;
	border-radius: 4px;
	color: #304455;
}
</style>
