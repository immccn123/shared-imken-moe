<script lang="ts">
    import MarkdownIt from "markdown-it";
    import introduction from "./introduction.md?raw";
    import Title from "../components/Title.svelte";
</script>

<Title content="欢迎！" />

<div class="container p-4">
    <article class="prose">
        <h1>欢迎！</h1>
        {@html new MarkdownIt().render(introduction)}
    </article>
</div>
