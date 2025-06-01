<script lang="ts">

</script>

<div class="navbar">
    <h1>
        Ren and the Stimpies
    </h1>
    <nav>
        <a class="link" href="/">Home</a>
        <a class="link" href="/about">About</a>
        <a class="link" href="/music">Music</a>
        <a class="link" href="/contact">Contact</a>
    </nav>
    <hr class="line"/>
    <hr class="line"/>
</div>

<style>
    .navbar {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100vw;
    }

    .link {
        color: inherit;
        text-decoration: inherit;
    }

    .link:hover {
        text-decoration: underline;
    }

    .line {
        width: 100%;
        height: 1px;
        border-width: 0;
        background-color: var(--color-primary);
        margin: 3px;
    }
</style>