<template>
	<button type="button" @click="confirm">{{ buttonText }}</button>
</template>

<script>
import Swal from "sweetalert2";
export default {
	name: "VueConfirmButton",
	props: {
		buttonText: {
			required: true,
			type: String,
		},
		confirmationText: {
			required: true,
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
				title: this.confirmationText,
				showCancelButton: true,
				confirmButtonText: this.confirmButtonText,
				cancelButtonText: this.cancelButtonText,
			}).then((result) => {
				/* Read more about isConfirmed, isDenied below */
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
