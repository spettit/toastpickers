<script>
	import ToastEditor from '$lib/ToastEditor.svelte';
	let content = '';
</script>

<h1>Heading</h1>
<div>
	<ToastEditor bind:htmlOutput={content} height="300px" />
</div>

{content}

<style>
</style>
