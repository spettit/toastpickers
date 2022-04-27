<script>
	import ToastEditor from '$lib/DatePicker.svelte';
	let theDate;
</script>

<h1>Heading</h1>
<div>
	<ToastEditor bind:theDate />
</div>
{theDate}

<!-- {content} -->
<style>
</style>
