<template><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64" :width="width" :height="height"><g stroke-linecap="round" stroke-linejoin="round" stroke-width="2" fill="#da7f8f" stroke="#da7f8f"><path d="M38,39H26A18,18,0,0,0,8,57H8s9,4,24,4,24-4,24-4h0A18,18,0,0,0,38,39Z" fill="none" stroke="#da7f8f"></path><path d="M19,17.067a13,13,0,1,1,26,0C45,24.283,39.18,32,32,32S19,24.283,19,17.067Z" fill="none"></path></g></svg></template>

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