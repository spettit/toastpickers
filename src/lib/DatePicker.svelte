<script>
	import { onMount } from 'svelte';

	import DatePicker from 'tui-date-picker';

	import 'tui-date-picker/dist/tui-date-picker.css';

	export let theDate = new Date();

	let instance;

	onMount(() => {
		const container = document.getElementById('tui-date-picker-container');
		const target = document.getElementById('tui-date-picker-target');

		instance = new DatePicker(container, {
			date: theDate,
			input: {
				element: target,
				format: 'dd-MM-yyyy'
			}
		});

		instance.on('change', () => (theDate = instance.getDate()));
	});
</script>

<div class="tui-datepicker-input tui-datetime-input tui-has-focus">
	<input type="text" id="tui-date-picker-target" aria-label="Date-Time" />
	<span class="tui-ico-date" />
</div>

<div id="tui-date-picker-container" style="margin-top: -1px;" />

<!-- this is the calendar container -->
<style>
</style>
