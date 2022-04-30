<script>
	import DatePicker from '$lib/DatePicker.svelte';
	import DateRangePicker from '$lib/DateRangePicker.svelte';
	let theDate;
</script>

<h1>Date and Time Pickers</h1>
<div>
	<DatePicker bind:theDate withTime={false} />
</div>
<span class="display">
	{theDate}
</span>

<div>
	<DateRangePicker bind:theDate />
</div>

<div>ieieieieiieieie</div>

<style>
	.display {
		margin-top: 30px;
		background-color: lightslategrey;
		color: white;
	}
</style>
