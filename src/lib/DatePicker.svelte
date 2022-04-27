<script>
	import { onMount } from 'svelte';

	import DatePicker from 'tui-date-picker';

	import 'tui-date-picker/dist/tui-date-picker.css';

	export let theDate = new Date();

	let container;
	let target;

	let datePicker;

	onMount(() => {
		// const container = document.getElementById('tui-date-picker-container');
		// const target = document.getElementById('tui-date-picker-target');

		datePicker = new DatePicker(container, {
			date: theDate,
			input: {
				element: target,
				format: 'dd-MM-yyyy'
			}
		});

		datePicker.on('change', () => (theDate = datePicker.getDate()));
	});
</script>

<div class="tui-datepicker-input tui-datetime-input tui-has-focus">
	<input type="text" aria-label="Date-Time" bind:this={target} />
	<span class="tui-ico-date" />
</div>

<div style="margin-top: -1px;" bind:this={container} />

<!-- this is the calendar container -->
<style>
</style>
