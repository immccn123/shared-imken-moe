<script lang="ts">
    import "../app.css";
    import { SaraProvider } from "saraui";
    import MdiMenu from "~icons/mdi/menu";
    import MdiClose from "~icons/mdi/close";
    // import MdiMoreHoriz from "~icons/mdi/more-horiz";
    import MenuLink from "./MenuLink.svelte";
</script>

<SaraProvider>
    <div class="drawer lg:drawer-open">
        <input id="sidebar-toggle" type="checkbox" class="drawer-toggle" />
        <div class="drawer-content">
            <div class="navbar bg-base-100 border-b shadow z-50 lg:hidden">
                <div class="flex-none lg:hidden">
                    <label
                        for="sidebar-toggle"
                        class="btn drawer-button btn-square btn-ghost"
                    >
                        <MdiMenu />
                    </label>
                </div>

                <div class="flex-1">
                    <a class="btn btn-ghost text-xl" href="/">
                        Imken's Data Nook
                    </a>
                </div>
            </div>
            <slot></slot>
        </div>
        <div class="drawer-side">
            <label
                for="sidebar-toggle"
                aria-label="close sidebar"
                class="drawer-overlay"
            ></label>

            <ul class="menu bg-base-100 w-56 min-h-full lg:border-r">
                <div class="mb-1 w-full max-lg:hidden">
                    <a class="btn btn-ghost text-xl" href="/">
                        Imken's Data Nook
                    </a>
                </div>
                <label
                    for="sidebar-toggle"
                    class="btn drawer-button btn-square btn-ghost lg:hidden mb-1"
                >
                    <MdiClose />
                </label>
                <MenuLink to="/">欢迎</MenuLink>
                <span class="menu-title">友情链接</span>
                <ul>
                    <MenuLink to="/links/list">链接列表</MenuLink>
                    <MenuLink to="/links/exchange">友链互换</MenuLink>
                </ul>
            </ul>
        </div>
    </div>
</SaraProvider>
