<script lang="ts">
	import Instagram from "$lib/icons/Instagram.svelte";
    import Tiktok from "./icons/Tiktok.svelte";
</script>

<footer>
    <hr class="line">
    <div class="content">
        <h3>Ren and<br>the Stimpies</h3>
        <a href="https://www.instagram.com/renandthestimpies/"><Instagram class="icon"/></a>
        <a href="https://www.instagram.com/renandthestimpies/"><Tiktok class="icon"/></a>
    </div>
</footer>

<style>
    footer {
        position: fixed;
        bottom: 2vw;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100vw;
    }

    h3 {
        margin: 0 3em 0 0;
    }

    .line {
        width: 100%;
        height: 1px;
        border-width: 0;
        margin: 1em;
        background-color: var(--color-text);
    }

    .content {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1em;
        width: 50%;
        min-width: 500px;
    }

    :global(.icon) {
        width: 2em;
        height: 2em;
        fill: var(--color-text);
    }
</style>