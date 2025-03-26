<script lang="ts">
    import { onMount } from "svelte";
    let deferredPrompt: any = null;
    let showButton = false;

    onMount(() => {
        window.addEventListener("beforeinstallprompt", (event) => {
            event.preventDefault(); // Evita que el navegador muestre el mensaje automáticamente
            deferredPrompt = event;
            showButton = true;
        });
    });

    async function installApp() {
        if (!deferredPrompt) return;
        deferredPrompt.prompt(); // Muestra el prompt de instalación
        const { outcome } = await deferredPrompt.userChoice;
        if (outcome === "accepted") {
            console.log("El usuario aceptó la instalación");
        } else {
            console.log("El usuario rechazó la instalación");
        }
        deferredPrompt = null;
        showButton = false;
    }
</script>

{#if showButton}
    <button on:click={installApp} class="install-button">
        📲 Instalar Aplicación
    </button>
{/if}

<style>
    .install-button {
        position: fixed;
        bottom: 20px;
        left: 20px;
        padding: 10px 15px;
        background-color: #0077b5;
        color: white;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        font-size: 1rem;
        box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
        z-index: 10000000;
    }

    .install-button:hover {
        background-color: #005f90;
    }
</style>
