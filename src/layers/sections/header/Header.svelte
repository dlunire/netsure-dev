<script lang="ts">
    import "./header.scss";
    import Logo from "../../icons/Logo.svelte";
    import Menu from "./menu/Menu.svelte";
    import type { Menu as MenuItem } from "../../../lib/interface/menu";

    export let menu: MenuItem[] = [];

    let open: boolean = false;
</script>

<header class="header">
    <div class="header__blackbar"></div>

    <nav class="header__nav header__nav--red" class:header__nav--open={open}>
        <div class="header__logo" class:header__logo--open={open}>
            <Logo />
        </div>
        <div class="header__menu header__menu--red">
            <Menu bind:open bind:menu />
        </div>
    </nav>
</header>
