<script lang="ts">
    import { socials } from '$lib/constants';
    import ThemeSelect from './ThemeSelect.svelte';

    export let variant: 'homepage' | 'docs' = 'homepage';

    const year = new Date().getFullYear()
</script>

{#if variant === 'homepage'}
    <footer class="web-main-footer u-position-relative u-margin-block-start-48">
        <ul class="u-flex u-gap-8">
            {#each socials as social}
                <li>
                    <a
                        href={social.link}
                        class="web-icon-button"
                        aria-label={social.label}
                        target="_blank"
                        rel="noopener noreferrer"
                    >
                        <span class={social.icon} aria-hidden="true" />
                    </a>
                </li>
            {/each}
        </ul>
        <div class="u-flex u-gap-16">
            <ul class="u-flex u-gap-8">
                <li><a class="web-link" href="/terms">Terms</a></li>
                <li><a class="web-link" href="/privacy">Privacy</a></li>
                <li><a class="web-link" href="/cookies">Cookies</a></li>
            </ul>
            <div>Copyright © {year} NeuroFin</div>
        </div>
    </footer>
{:else if variant === 'docs'}
    <footer
        class="web-main-footer is-with-bg-color u-margin-block-start-32 u-small u-position-relative"
    >
        <div class="web-main-footer-grid-1">
            <ul class="web-main-footer-grid-1-column-1 u-flex u-gap-8">
                {#each socials as social}
                    <li>
                        <a
                            href={social.link}
                            class="web-icon-button"
                            aria-label={social.label}
                            target="_blank"
                            rel="noopener noreferrer"
                        >
                            <span class={social.icon} aria-hidden="true" />
                        </a>
                    </li>
                {/each}
            </ul>
            <div class="web-main-footer-grid-1-column-2">
                <ThemeSelect />
            </div>
            <ul class="web-main-footer-grid-1-column-3 web-main-footer-links">
                <li>
                    <a href="/discord" target="_blank" rel="noopener noreferrer">Support</a>
                </li>
                <li>
                    <a href="https://appwrite.online" target="_blank" rel="noopener noreferrer"
                        >Status</a
                    >
                </li>

            </ul>
            <div class="web-main-footer-grid-1-column-4 web-main-footer-copyright">
                Copyright © {year} NeuroFin
            </div>
        </div>
    </footer>
{/if}

<style lang="scss">
  .web-icon-button {
    display: grid;
  }
</style>