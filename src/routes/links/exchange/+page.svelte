<script lang="ts">
    import MarkdownIt from "markdown-it";
    import requirement from "./requirement.md?raw";
    import Title from "../../../components/Title.svelte";
</script>

<Title content="友链互换" />

<div class="container p-4">
    <article class="prose">
        <h1>友链互换</h1>
        {@html new MarkdownIt().render(requirement)}
    </article>
</div>
