<script>
    import Title from "../../../components/Title.svelte";
</script>

<Title content="友链列表" />

<div class="container p-4">
    <article class="prose">
        <h1>友链列表</h1>
    </article>

    {#await import("https://data.imken.moe/links.js")}
        <p class="text-center">
            <span class="loading loading-ring loading-lg"></span>
        </p>
    {:then links}
        <div class="overflow-x-auto">
            <table class="table">
                <thead>
                    <tr>
                        <th>Site</th>
                        <th>Description</th>
                    </tr>
                </thead>
                <tbody>
                    {#each links.default as { url, name, description, avatar }}
                        <tr>
                            <td>
                                <div class="flex items-center gap-3">
                                    <div class="avatar">
                                        <div
                                            class="mask mask-squircle h-12 w-12 fallback-img"
                                        >
                                            <img src={avatar} alt={name} />
                                        </div>
                                    </div>
                                    <div>
                                        <div class="font-bold">
                                            {name}
                                        </div>
                                        <div class="text-sm opacity-50">
                                            <a href={url}>{url}</a>
                                        </div>
                                    </div>
                                </div>
                            </td>
                            <td>{description}</td>
                        </tr>
                    {/each}
                </tbody>
                <tfoot>
                    <tr>
                        <th>Site</th>
                        <th>Description</th>
                    </tr>
                </tfoot>
            </table>
        </div>
    {/await}
</div>
