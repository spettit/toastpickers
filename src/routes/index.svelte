<script>
	import DatePicker from '$lib/DatePicker.svelte';
	let theDate;
</script>

<h1>Heading</h1>
<div>
	<DatePicker bind:theDate />
</div>
{theDate}

<style>
</style>
