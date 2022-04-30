<script>
	import { add } from 'date-fns';
	import { onMount } from 'svelte';

	// import DatePicker from 'tui-date-picker';

	import 'tui-date-picker/dist/tui-date-picker.min.css';

	// import 'tui-time-picker/dist/tui-time-picker.css';

	export let theStartDate = new Date();

	let theEndDate = add(theStartDate, { days: 1 });

	onMount(async () => {
		const DatePicker = await import('tui-date-picker');
		let dateRangePicker = DatePicker.createRangePicker({
			startpicker: {
				date: theStartDate,
				input: '#startpicker-input',
				container: '#startpicker-container'
			},
			endpicker: {
				date: theEndDate,
				input: '#endpicker-input',
				container: '#endpicker-container'
			},
			format: 'dd-MM-yyyy',
			selectableRanges: [
				[
					theStartDate,
					new Date(theStartDate.getFullYear() + 1, theStartDate.getMonth(), theStartDate.getDate())
				]
			]
		});

		dateRangePicker.on('change:start', () => {
			dateRangePicker.setEndDate(add(dateRangePicker.getStartDate(), { days: 1 }));
			console.log(dateRangePicker.getEndDate());
		});
		const containers = Array.from(document.getElementsByClassName('tui-datepicker'));
		containers.forEach((c) => (c.style.zIndex = 100));
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
