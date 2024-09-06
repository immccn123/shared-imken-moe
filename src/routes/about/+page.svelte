<script lang="ts">
    import MarkdownIt from "markdown-it";
    import intro from "./introduction.md?raw";
    import Title from "../../components/Title.svelte";
</script>

<Title content="关于 Imken" />

<div class="container p-4">
    <article class="prose">
        <h1>关于 Imken</h1>
        {@html new MarkdownIt().render(intro)}
    </article>
</div>
