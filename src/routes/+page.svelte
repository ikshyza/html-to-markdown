<script>
    import {tipexEditor} from '@friendofsvelte/tipex';

    import TurndownService from 'turndown';
    import Markdown from "$lib/Markdown.svelte";
    import Editor from "$lib/Editor.svelte";
    const turndownService = new TurndownService();

    let htmlContent = `Paste your <b>HTML</b> content here.`;
    $: convertedMarkdown = turndownService.turndown($tipexEditor ? $tipexEditor.getHTML() : htmlContent);
</script>

<svelte:head>
    <meta name="description" content="HTML to Markdown Converter">
    <meta name="keywords" content="HTML, Markdown, Converter, Web Tool">
    <meta name="author" content="Your Name">
    <meta name="robots" content="index, follow">
    <meta name="og:title" content="HTML to Markdown Converter">
    <meta name="og:description" content="Convert HTML to Markdown with this online tool.">
    <meta name="og:type" content="website">
    <title>HTML to Markdown Converter</title>
</svelte:head>

<div class="main-container">
    <div class="editor-wrapper">
        <Editor bind:htmlContent/>
        <Markdown bind:convertedMarkdown/>
    </div>
</div>

<style>
    .main-container {
        min-height: 100vh;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 3rem;
    }

    .editor-wrapper {
        width: 100%;
        gap: 5rem;
        flex-direction: column;
        display: flex;
        justify-content: center;
        height: 80vh;

        @media screen and (min-width: 780px) {
            max-width: 90vw;
            gap: 3rem;
            flex-direction: row;
            max-width: 90vw;
        }
    }
</style>
