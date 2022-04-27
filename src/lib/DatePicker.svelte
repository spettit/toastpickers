<script>
	import { onMount } from 'svelte';

	import DatePicker from 'tui-date-picker';

	import 'tui-date-picker/dist/tui-date-picker.css';

	import 'tui-time-picker/dist/tui-time-picker.css';

	export let theDate = new Date();
	export let withTime = false; //

	let container;
	let target;

	let datePicker;

	onMount(() => {
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

<!-- this is the calendar container -->
<style>
</style>
