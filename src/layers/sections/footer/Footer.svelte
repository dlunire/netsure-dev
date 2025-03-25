<script lang="ts">
    import type { Menu } from "../../../lib/interface/menu";
    import IconForm from "../../icons/IconForm.svelte";
    import IconPortfolio from "../../icons/IconPortfolio.svelte";
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

            <ul class="footer__menu">
                <li class="footer__list">
                    <a
                        href="https://drive.google.com/file/d/18ovkKrJatJdvUdNifLplUBV2SsTjjcCV/view"
                        target="_blank"
                        class="footer__menu-link"
                    >
                        <IconPortfolio />
                        <span>Portafolio</span>
                    </a>
                </li>

                <li class="footer__list">
                    <a
                        href="https://drive.google.com/file/d/1jLmSbZ3H8TutQbmLx67Wbue0r4Q5-H_H/view"
                        target="_blank"
                        class="footer__menu-link"
                    >
                        <IconPortfolio />
                        <span>Formato de propuesta económica</span>
                    </a>
                </li>

                <li class="footer__list">
                    <a
                        href="https://docs.google.com/forms/d/e/1FAIpQLSd-E2T6CjR2leReUoF16Ku_klbpUykN2G0LJpG-iCnPkbP06w/viewform"
                        target="_blank"
                        class="footer__menu-link"
                    >
                        <IconForm />
                        <span>Formulario de contacto</span>
                    </a>
                </li>
            </ul>
        </div>

        <div class="footer__item">
            <h2 class="footer__title">
                <span>Redes Sociales</span>
            </h2>

            <ul class="footer__menu"></ul>
        </div>
    </div>

    <div class="footer__author"></div>
</footer>
