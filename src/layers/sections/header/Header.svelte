<script lang="ts">
    import "./header.scss";
    import Logo from "../../icons/Logo.svelte";
    import Menu from "./menu/Menu.svelte";

    let openMenu: boolean = false;

    /**
     * Menu Button
     *
     * @param event Evento del Mouse
     */
    function handle(event: MouseEvent): void {
        const { target: button } = event;

        if (!(button instanceof HTMLButtonElement)) {
            return;
        }

        openMenu = !openMenu;
        openMenu = openMenu;
    }

    $: console.log({ openMenu });
</script>

<header class="header">
    <div class="header__blackbar"></div>

    <nav class="header__nav header__nav--red">
        <div class="header__logo">
            <Logo />
        </div>
        <div class="header__menu header__menu--red">
            <Menu />
            <button
                class="button button--menu"
                aria-label="menu"
                on:click={handle}
                class:open={openMenu}
            >
                <span></span><span></span><span></span>
            </button>
        </div>
    </nav>
</header>

<style lang="scss">
    .open {
        border-radius: 2px;

        span {
            width: 20px;
            --y: 46.7%;
            &:first-of-type {
                transform: rotate(45deg);
                animation: 300ms ease open-menu-1 ease forwards;
            }

            &:nth-of-type(2) {
                opacity: 0;
            }

            &:last-of-type {
                transform: rotate(-45deg);
                animation: 300ms ease open-menu-2 ease forwards;
            }
        }
    }
</style>
