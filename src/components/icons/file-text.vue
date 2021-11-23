<template><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" :width="width" :height="height"><g stroke-width="1" fill="#da7f8f" stroke="#da7f8f"><line fill="none" stroke-linecap="round" stroke-linejoin="round" x1="4.5" y1="11.5" x2="11.5" y2="11.5"></line> <line fill="none" stroke-linecap="round" stroke-linejoin="round" x1="4.5" y1="8.5" x2="11.5" y2="8.5"></line> <line fill="none" stroke-linecap="round" stroke-linejoin="round" x1="4.5" y1="5.5" x2="6.5" y2="5.5"></line> <polygon fill="none" stroke="#da7f8f" stroke-linecap="round" stroke-linejoin="round" points="9.5,0.5 1.5,0.5 1.5,15.5 14.5,15.5 14.5,5.5 "></polygon> <polyline fill="none" stroke="#da7f8f" stroke-linecap="round" stroke-linejoin="round" points="9.5,0.5 9.5,5.5 14.5,5.5 "></polyline></g></svg></template>

<script>
export default {
	props: {
		width: {
			type: [Number, String],
			default: "100%"
		},
		height: {
			type: [Number, String],
			default: "100%"
		}
	}
}
</script>