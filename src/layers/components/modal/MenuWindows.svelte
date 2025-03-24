<script lang="ts">
    import type { Menu } from "../../../lib/interface/menu";
    import "./scss/menu.scss";
    export let open: boolean = false;
    export let menu: Menu[] = [];

    let modal: HTMLElement | null = null;

    /**
     * Agrega la ventana modal en el cuerpo del documento
     *
     * @param element
     */
    function loadModal(element: HTMLElement | null): void {
        document.body.removeAttribute("style");

        if (!(element instanceof HTMLElement)) {
            return;
        }

        document.body.appendChild(element);

        if (open) {
            document.body.setAttribute("style", "overflow: hidden");
            return;
        }
    }

    $: loadModal(modal);
    $: console.log({ open });
</script>

{#if open}
    <div class="modal-container" bind:this={modal}>
        <section class="modal">
            <section class="modal__container">
                <ul class="menu menu--horizontal">
                    {#each menu as item}
                        <li class="menu__item menu__item--horizontal">
                            <a
                                class="menu__link menu__link--horizontal"
                                href={item.link}
                                aria-label={item.label}
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
            </section>
        </section>
    </div>
{/if}
