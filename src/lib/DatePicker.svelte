<script>
	import { onMount } from 'svelte';

	import 'tui-date-picker/dist/tui-date-picker.min.css';

	import 'tui-time-picker/dist/tui-time-picker.min.css';

	export let theDate = new Date();
	export let withTime = false; //

	let container;
	let target;

	let datePicker;

	onMount(async () => {
		const DatePickerImport = await import('tui-date-picker');
		const DatePicker = DatePickerImport.default;
		datePicker = new DatePicker(container, {
			date: theDate,
			timePicker: withTime,
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

<style>
</style>
