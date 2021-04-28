<template>
	<button type="button" @click="confirm"><slot></slot></button>
</template>

<script>
import Swal from "sweetalert2";
export default {
	name: "VueConfirmButton",
	props: {
		dialogTitle: {
			required: true,
			type: String,
		},
		dialogText: {
			required: false,
			type: String,
		},
        confirmButtonText: {
            required: false,
            type: String,
            default: "Yes"
        },
        cancelButtonText: {
            required: false,
            type: String,
            default: "Cancel"
        },
	},
	methods: {
		confirm() {
			Swal.fire({
				title: this.dialogTitle,
                text: this.dialogText,
				showCancelButton: true,
				confirmButtonText: this.confirmButtonText,
				cancelButtonText: this.cancelButtonText,
			}).then((result) => {
				if (result.isConfirmed) {
					this.$emit("confirmed");
				}
                else {
                    this.$emit("canceled");
                }
			});
		},
	},
};
</script>

<style></style>