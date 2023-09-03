<script>
    import { Tipex } from "@friendofsvelte/tipex";
    import "@friendofsvelte/tipex/styles/app.css";
    import "@friendofsvelte/tipex/styles/Tipex.css";
    import "@friendofsvelte/tipex/styles/ProseMirror.css";
    import "@friendofsvelte/tipex/styles/Controls.css";
    import "@friendofsvelte/tipex/styles/EditLink.css";
    import "@friendofsvelte/tipex/styles/Tipex.css";

    let htmlContent = `
<p>This <a target="_blank" rel="noopener noreferrer" href="">content</a> is written by
<a target="_blank" rel="noopener noreferrer" href="http://bishwas.net/">Bishwas</a> in 2023.
</p>`;

    let convertedMarkdown = "";
</script>

<div class="main-container">
    <div class="editor-wrapper">
        <Tipex {htmlContent} class="tipex-editor" />
        <div class="markdown-editor">
            <textarea value={convertedMarkdown} />
        </div>
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
        display: flex;
        gap: 3rem;
    }

    .editor-wrapper :global(.tipex-editor) {
        margin-top: 0rem;
        margin-bottom: 0rem;
        height: 100%;
        height: 80vh;
    }

    .markdown-editor {
        height: 100%;
    }

    .markdown-editor textarea {
        height: 100%;
    }
</style>
