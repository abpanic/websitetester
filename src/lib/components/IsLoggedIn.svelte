<script lang="ts">
    export let classes = '';
</script>

<a href="https://neurofin.cloud" class={`web-button ${classes}`}>
    <span class="logged-in"><slot name="isLoggedIn">Go to Console</slot></span>
    <span class="not-logged-in"><slot name="isNotLoggedIn">Get started</slot></span>
</a>

<style lang="scss">
    :global(body[data-logged-in]) {
        .logged-in {
            display: block;
        }
        .not-logged-in {
            display: none;
        }
    }
    .not-logged-in {
        display: block;
    }
    .logged-in {
        display: none;
    }
</style>
