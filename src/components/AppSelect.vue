<template>
	<a-select
		@change="handleChange"
		v-model:value="valueData"
		:placeholder="placeholder"
	>
		<a-select-option
			v-for="item in dicData"
			:value="item.code"
			:key="item.code"
		>
			{{ item.label }}
		</a-select-option>
	</a-select>
</template>
<script lang="ts">
export default {
	name: "app-select"
};
</script>
<script setup lang="ts">
import { ref, watch } from "vue";

const props = defineProps({
	value: String,
	dicName: {
		type: String,
		default: ""
	},
	placeholder: String
});
const emit = defineEmits(["update:value"]);

const dicData = ref([
	{
		code: "001",
		label: "选项1"
	},
	{
		code: "002",
		label: "选项2"
	},
	{
		code: "003",
		label: "选项3"
	}
]);
const valueData = ref(props.value);

const handleChange = (value: string) => {
	emit("update:value", value);
};
</script>
