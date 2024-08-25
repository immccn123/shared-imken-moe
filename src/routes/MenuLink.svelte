<script lang="ts">
    import { page } from "$app/stores";

    $: pathname = $page.url.pathname;

    export let to: string;
</script>

<li>
    <a href={to} class:active={pathname === to} class="disabled">
        <slot></slot>
    </a>
</li>
