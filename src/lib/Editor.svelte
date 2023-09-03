<script>
    import { Tipex } from "@friendofsvelte/tipex";

    import "@friendofsvelte/tipex/styles/app.css";
    import "@friendofsvelte/tipex/styles/Tipex.css";
    import "@friendofsvelte/tipex/styles/ProseMirror.css";
    import "@friendofsvelte/tipex/styles/Controls.css";
    import "@friendofsvelte/tipex/styles/EditLink.css";
    import "@friendofsvelte/tipex/styles/Tipex.css";

    export let htmlContent;
</script>

<div class="html-editor">
    <h2 class="c-h2">HTML Text</h2>
    <Tipex {htmlContent} class="tipex-editor" />
</div>


<style>
    .html-editor :global(.tipex-editor) {
        margin-top: 0rem;
        margin-bottom: 0rem;
        max-height: 75vh;
        gap: 0px;
        height: 100%;
        width: 100%;
    }

    .html-editor :global(.tipex-editor .tipex-content-section) {
        overflow-y: scroll;
    }

    .html-editor :global(.tipex-editor .tipex-content-section pre) {
        border-radius: 19px;
    }

    
    .html-editor :global(.tipex-editor .tipex-content-section pre code) {
        background-color: rgba(240, 248, 255, 0.144);
        color: rgb(255, 255, 255);
    }

    .html-editor {
        width: 100%;
        @media screen and (min-width: 780px) {
            width: 60%;
        }
    }
</style>