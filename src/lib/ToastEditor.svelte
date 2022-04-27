<script>
	import Editor from '@toast-ui/editor';
	import '@toast-ui/editor/dist/toastui-editor.css';

	export let htmlOutput = '';
	export let height = '400px';
	export let code = false;
	let editor;

	const createEditor = (node) => {
		editor = new Editor({
			el: node,
			events: { change: handleChange },
			initialEditType: 'wysiwyg',
			usageStatistics: false,
			hideModeSwitch: true,
			initialValue: htmlOutput,
			height: height
		});
		if (!code) {
			editor.removeToolbarItem('code');
			editor.removeToolbarItem('codeblock');
		}
	};

	const handleChange = () => {
		htmlOutput = editor.getHTML();
	};
</script>

<div id="editor" use:createEditor />

<style>
</style>
