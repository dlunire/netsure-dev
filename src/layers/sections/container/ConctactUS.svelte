<script>
    import IconContact from "../../icons/IconContact.svelte";
</script>

<section class="section section--contact-us" id="contact">
    <div class="section__inner">
        <h2 class="section__title">
            <IconContact />
            <span>CONTACTO</span>
        </h2>

        <div class="section__columns">
            <section class="section__column">
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1011716.425566044!2d-73.50348077599179!3d7.8932596686915755!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xaa6fb9e0ad23dcb7%3A0x30348f0607bf930b!2sNORSIRE%20ESP%20SAS!5e0!3m2!1ses-419!2sco!4v1742665694185!5m2!1ses-419!2sco"
                    width="600"
                    height="450"
                    style="border:0;"
                    allowfullscreen={true}
                    loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"
                    title="Ubicación"
                ></iframe>
            </section>
        </div>
    </div>
</section>
