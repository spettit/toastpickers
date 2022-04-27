# toasteditor

Add a simple wysiwyg editor to your svelte project

This is a wrapper around Toast UI Editor

Usage

    npm install toasteditor@latest

Svelte component

    <script>
        import ToastEditor from "toasteditor";
        let content = '';
    </script>

    <div>
        <ToastEditor bind:htmlOutput={content} height="300px" code="true"/>
    </div>

props: default

    htmlOutput      ""
    height          "400px"
    code            false

can override css in global.css with !important

    .toastui-editor-contents h1 {
    color: red !important;
    }
