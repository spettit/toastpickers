# toastcomponents

Add date and time pickers to svelte projects

This is a wrapper around Toast UI Components

Usage

    npm install toastcomponents@latest

Svelte component

    <script>
        import {DatePicker} from "toastcomponents";
        let theDate;
    </script>

    <div>
        <DatePicker bind:theDatet={theDate} />
    </div>

props: default

    theDate = new Date()
