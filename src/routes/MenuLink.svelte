<script lang="ts">
    import { page } from "$app/stores";

    $: pathname = $page.url.pathname;

    export let to: string;
</script>

<li>
    <a class:active={pathname === to} href={to}>
        <slot></slot>
    </a>
</li>
