<script lang="ts">
    import type { Menu } from "../../../lib/interface/menu";

    export let menu: Menu[] = [];
</script>

<footer class="footer">
    <div class="footer__inner">
        <div class="footer__item">
            <ul class="footer__menu">
                {#each menu as item}
                    {#if item.icon}
                        <svelte:component this={item.icon} />
                    {/if}

                    <a href={item.link} aria-label={item.label}>{item.label}</a>
                {/each}
            </ul>
        </div>
    </div>

    <div class="footer__author"></div>
</footer>
