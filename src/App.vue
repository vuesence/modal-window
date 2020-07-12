<template>
	<div id="app">
		<p>Click the button to open modal window</p>
		<button @click="showModal = true">Open Modal</button>

    <!-- All the props (close-on-escape, close-on-outside-click, show-x-mark) are optional
    Below listed their default values -->
		<modal-window
			:visible="showModal"
			:close-on-escape="true"
			:close-on-outside-click="true"
			:show-x-mark="true"
			@close="showModal = false"
		>
			<h2>Modal window</h2>
			<p>Here be content</p>
		</modal-window>
	</div>
</template>

<script>
import ModalWindow from "./components/ModalWindow.vue";

export default {
	name: "App",
	components: {
		ModalWindow
	},
	data() {
		return {
			showModal: false
		};
	}
};
</script>

<style>
html,
body {
	height: 100%;
	padding: 0;
	margin: 0;
}
body {
	display: flex;
	justify-content: center;
	align-items: center;
}
#app {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
</style>
