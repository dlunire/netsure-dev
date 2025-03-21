<script lang="ts">
    import Logo from "../../icons/Logo.svelte";
    import "./header.scss";
    import Menu from "./menu/Menu.svelte";
</script>

<header class="header">
    <div class="header__blackbar"></div>

    <nav class="header__nav header__nav--red">
        <div class="header__logo">
            <Logo />
        </div>
        <div class="header__menu header__menu--red">
            <Menu />
        </div>
    </nav>
</header>
