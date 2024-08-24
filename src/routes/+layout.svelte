<script lang="ts">
    import "../app.css";
    import { SaraProvider } from "saraui";
    import MdiMenu from "~icons/mdi/menu";
    // import MdiMoreHoriz from "~icons/mdi/more-horiz";
    import MenuLink from "./MenuLink.svelte";
</script>

<SaraProvider>
    <div class="navbar bg-base-100 border-b shadow z-50">
        <div class="flex-none lg:hidden">
            <label
                for="sidebar-toggle"
                class="btn drawer-button btn-square btn-ghost"
            >
                <MdiMenu />
            </label>
        </div>
        <div class="flex-1">
            <a class="btn btn-ghost text-xl" href="/"> Imken's Data Nook </a>
        </div>
    </div>
    <div class="drawer lg:drawer-open">
        <input id="sidebar-toggle" type="checkbox" class="drawer-toggle" />
        <div class="drawer-content">
            <slot></slot>
        </div>
        <div class="drawer-side">
            <label
                for="sidebar-toggle"
                aria-label="close sidebar"
                class="drawer-overlay"
            ></label>
            <ul class="menu bg-base-100 w-56 min-h-full border-r">
                <MenuLink to="/">欢迎</MenuLink>
                <ul class="p-3 text-xs text-primary-content">友情链接</ul>
                <MenuLink to="/links/list">链接列表</MenuLink>
                <MenuLink to="/links/exchange">友链互换</MenuLink>
            </ul>
        </div>
    </div>
</SaraProvider>
