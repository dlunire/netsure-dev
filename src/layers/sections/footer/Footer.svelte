<script lang="ts">
    import type { Menu } from "../../../lib/interface/menu";
    export let menu: Menu[] = [];
</script>

<footer class="footer">
    <div class="footer__inner">
        <div class="footer__item">
            <h2 class="footer__title">
                <span>Menú principal</span>
            </h2>
            <ul class="footer__menu">
                {#each menu as item}
                    <li class="footer__list">
                        <a
                            href={item.link}
                            aria-label={item.label}
                            class="footer__menu-link"
                        >
                            {#if item.icon}
                                <svelte:component this={item.icon} />
                            {/if}
                            <span>
                                {item.label}
                            </span>
                        </a>
                    </li>
                {/each}
            </ul>
        </div>

        <div class="footer__item">
            <h2 class="footer__title">
                <span>Enlaces externos</span>
            </h2>

            <ul class="footer__menu"></ul>
        </div>
    </div>

    <div class="footer__author"></div>
</footer>
