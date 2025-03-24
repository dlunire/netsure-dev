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

    /**
     * Cierra el menú de navegación
     */
    function handle(): void {
        open = false;
    }

    $: loadModal(modal);
</script>

{#if open}
    <div class="modal-container" bind:this={modal}>
        <section class="modal">
            <section class="modal__container">
                <h2 class="modal__title">
                    <span>Menú principal</span>
                </h2>
                <ul class="menu menu--horizontal">
                    {#each menu as item}
                        <li class="menu__item menu__item--horizontal">
                            <a
                                class="menu__link menu__link--horizontal"
                                href={item.link}
                                aria-label={item.label}
                                on:click={handle}
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

                <h2 class="modal__title">
                    <span>Enlaces externos</span>
                </h2>
            </section>
        </section>
    </div>
{/if}
