<template><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" :width="width" :height="height"><g stroke-linecap="round" stroke-linejoin="round" stroke-width="2" fill="#da7f8f" stroke="#da7f8f"><path d="M38,46V33.39A17.992,17.992,0,1,0,8,20v2L4,30l4,2v6a4,4,0,0,0,4,4h8v4" fill="none" stroke="#da7f8f"></path><circle cx="26" cy="20" r="7" fill="none"></circle><line x1="26" y1="13" x2="26" y2="10" fill="none"></line><line x1="30.95" y1="15.05" x2="33.071" y2="12.929" fill="none"></line><line x1="33" y1="20" x2="36" y2="20" fill="none"></line><line x1="30.95" y1="24.95" x2="33.071" y2="27.071" fill="none"></line><line x1="26" y1="27" x2="26" y2="30" fill="none"></line><line x1="21.05" y1="24.95" x2="18.929" y2="27.071" fill="none"></line><line x1="19" y1="20" x2="16" y2="20" fill="none"></line><line x1="21.05" y1="15.05" x2="18.929" y2="12.929" fill="none"></line><circle cx="26" cy="20" r="2" fill="none"></circle></g></svg></template>

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