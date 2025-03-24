<script lang="ts">
    import "./header.scss";
    import Logo from "../../icons/Logo.svelte";
    import Menu from "./menu/Menu.svelte";

    let open: boolean = false;
</script>

<header class="header">
    <div class="header__blackbar"></div>

    <nav class="header__nav header__nav--red" class:header__nav--open={open}>
        <div class="header__logo">
            <Logo />
        </div>
        <div class="header__menu header__menu--red">
            <Menu bind:open />
        </div>
    </nav>
</header>
