<template><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" :width="width" :height="height"><g stroke-width="1" fill="#da7f8f" stroke="#da7f8f"><rect x="0.5" y="0.5" width="6" height="6" rx="1" fill="none" stroke="#da7f8f" stroke-linecap="round" stroke-linejoin="round"></rect><rect x="9.5" y="0.5" width="6" height="6" rx="1" fill="none" stroke-linecap="round" stroke-linejoin="round"></rect><rect x="0.5" y="9.5" width="6" height="6" rx="1" fill="none" stroke-linecap="round" stroke-linejoin="round"></rect><rect x="9.5" y="9.5" width="6" height="6" rx="1" fill="none" stroke="#da7f8f" stroke-linecap="round" stroke-linejoin="round"></rect> </g></svg></template>

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