<template>
	<div class="p-2 button d-flex justify-content-center align-items-center" @click="selectAnswer" :class="{ selected: isSelected}">
		<p class="answer-text">{{ answer }}</p>
	</div>
</template>

<script>
export default {
	props: {
		answer: {
			type: String,
			required: true,
		},
		isSelected: {
			type: Boolean,
			default: false,
		},
	},

	methods: {
		selectAnswer() {
			this.$emit("answered", this.answer);
		},
	},
};
</script>

<style scoped>
.button {
	width: 100%;
	background-color: var(--primary);
	border: 1px solid var(--secondary);
	border-radius: 10px;
	margin: 2px;
	transition: all 0.3s ease-in;
}
.button:hover {
	background-color: var(--selected);
	cursor: pointer;
}

.selected {
	background-color: var(--selected);
}

.answer-text {
	margin: 0;
	padding: 0;
	text-align: center;
	font-weight: 400;
	font-size: large;
}
</style>
