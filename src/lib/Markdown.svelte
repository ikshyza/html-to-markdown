<script>
    export let convertedMarkdown;

    let isCopied = false;
    let copyTimeout;
    function copyToClipboard() {
        isCopied = true;
        navigator.clipboard.writeText(convertedMarkdown);
        copyTimeout = setTimeout(() => {
            isCopied = false;
            clearTimeout(copyTimeout);
        }, 1000);
    }
</script>

<div class="markdown-editor">
    <h2 class="c-h2">Markdown Text</h2>
    <textarea value={convertedMarkdown} />
    <button on:click={copyToClipboard}>
        {#if isCopied}
            Copied!
        {:else}
            Copy
        {/if}
    </button>
</div>

<style>
    .markdown-editor {
        display: flex;
        flex-direction: column;
        justify-content: start;
        width: 100%;
        height: 100%;
        @media screen and (min-width: 780px) {
            width: 40%;
        }
    }
    .markdown-editor textarea {
        border-radius: 1%;
        height: 100%;
        width: 100%;
        padding: 7px;
        outline: none;
        margin-bottom: 12px;
    }

    .markdown-editor textarea:focus {
        outline: 4px solid rgb(24, 161, 240);
    }

    .markdown-editor textarea:active {
        outline: 4px solid rgb(56, 152, 207);
    }
    .markdown-editor button {
        background-color: #538ece7d;
        color: #000017;
        border: none;
        border-radius: 4px; 
        padding: 10px 20px;
        cursor: pointer;
        width: fit-content;
        margin-left: auto;
    }

    .markdown-editor button:hover {
        background-color: #0056b3; /* Change the background color on hover */
    }
</style>
