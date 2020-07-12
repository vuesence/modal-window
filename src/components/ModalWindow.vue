<template>
	<transition name="modal">
		<div v-if="visible" class="vmw-modal-overlay">
			<div ref="overlay" class="vmw-modal-wrapper">
				<div class="vmw-modal-container">
					<slot></slot>
					<div
						v-if="showXMark"
						class="vmw-close-sign"
						@click="$emit('close')"
					>
						&#x274c;
					</div>
				</div>
			</div>
		</div>
	</transition>
</template>

<script>
export default {
	name: "ModalWindow",
	props: {
		visible: Boolean,
		closeOnEscape: {
			type: Boolean,
			default: true
		},
		closeOnOutsideClick: {
			type: Boolean,
			default: true
		},
		showXMark: {
			type: Boolean,
			default: true
		}
	},
	watch: {
		visible() {
			if (this.visible) {
				this.$nextTick(() => {
					if (this.closeOnOutsideClick) {
						this.$refs.overlay.addEventListener("click", e => {
							if (e.target == this.$refs.overlay) {
								this.$emit("close");
							}
						});
					}
					if (this.closeOnEscape) {
						document.addEventListener("keydown", event => {
							if (event.key === "Escape") {
								this.$emit("close");
							}
						});
					}
				});
			}
		}
	}
};
</script>

<style>
.vmw-modal-overlay {
	position: fixed;
	z-index: 9998;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.5);
	display: table;
	transition: opacity 0.3s ease;
}

.vmw-modal-wrapper {
	display: table-cell;
	vertical-align: middle;
}

.vmw-modal-container {
	width: 300px;
	margin: 0px auto;
	padding: 20px 30px 40px;
	background-color: #fff;
	border-radius: 2px;
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
	transition: all 0.3s ease;
	font-family: Helvetica, Arial, sans-serif;
	position: relative;
}

.modal-enter {
	opacity: 0;
}

.modal-leave-active {
	opacity: 0;
}

.modal-enter .vmw-modal-container,
.modal-leave-active .vmw-modal-container {
	-webkit-transform: scale(1.1);
	transform: scale(1.1);
}

.vmw-close-sign {
	content: "";
	position: absolute;
	color: #bbb;
	font-weight: bold;
	top: 0;
	right: 0;
	padding: 12px;
	cursor: pointer;
	transition: all 0.3s ease-out;
	font-size: 1.3em;
}

.vmw-close-sign:hover {
	color: #444;
}
</style>
