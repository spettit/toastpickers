<script>
	import { onMount } from 'svelte';

	import DatePicker from 'tui-date-picker';

	import 'tui-date-picker/dist/tui-date-picker.css';

	import 'tui-time-picker/dist/tui-time-picker.css';

	export let theDate = new Date();
	// export let withTime = false; //

	let container;
	let target;

	// let dateRangePicker;

	onMount(() => {
		let dateRangePicker = DatePicker.createRangePicker({
			startpicker: {
				date: theDate,
				input: '#startpicker-input',
				container: '#startpicker-container'
			},
			endpicker: {
				date: theDate,
				input: '#endpicker-input',
				container: '#endpicker-container'
			},
			selectableRanges: [
				[theDate, new Date(theDate.getFullYear() + 1, theDate.getMonth(), theDate.getDate())]
			]
		});
		console.log(dateRangePicker);
	});
</script>

<div class="tui-datepicker-input tui-datetime-input tui-has-focus">
	<input id="startpicker-input" type="text" aria-label="Date" />
	<span class="tui-ico-date" />
	<div id="startpicker-container" style="margin-left: -1px;" />
</div>
<span>to</span>
<div class="tui-datepicker-input tui-datetime-input tui-has-focus">
	<input id="endpicker-input" type="text" aria-label="Date" />
	<span class="tui-ico-date" />
	<div id="endpicker-container" style="margin-left: -1px;" />
</div>
