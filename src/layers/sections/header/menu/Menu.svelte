<script lang="ts">
    import type { SvelteComponent } from "svelte";
    import "./menu.scss";
    import IconContact from "../../../icons/IconContact.svelte";
    import IconService from "../../../icons/IconService.svelte";
    import IconAbout from "../../../icons/IconAbout.svelte";
    import IconHome from "../../../icons/IconHome.svelte";

    export let vertical: boolean = false;

    interface Menu {
        label: string;
        link: string;
        icon?: typeof SvelteComponent;
    }

    export let menu: Menu[] = [
        {
            label: "HOME",
            link: "#home",
            icon: IconHome as typeof SvelteComponent,
        },
        {
            label: "NOSOTROS",
            link: "#about",
            icon: IconAbout as typeof SvelteComponent,
        },
        {
            label: "SERVICIOS",
            link: "#services",
            icon: IconService as typeof SvelteComponent,
        },
        {
            label: "CONTACTO",
            link: "#contact",
            icon: IconContact as typeof SvelteComponent,
        },
    ];
</script>

{#if vertical}
    <ul class="menu">
        {#each menu as item}
            <li class="menu__item menu__item--vertical">
                {#if item.icon}
                    <svelte:component this={item.icon} />
                {/if}

                <span>{item.label}</span>
            </li>
        {/each}
    </ul>
{:else}
    <ul class="menu">
        {#each menu as item}
            <li class="menu__item menu__item--white">
                <a href={item.link} class="menu__link menu__link--white">
                    {#if item.icon}
                        <svelte:component this={item.icon} />
                    {/if}
                    <span>{item.label}</span>
                </a>
            </li>
        {/each}
    </ul>
{/if}
