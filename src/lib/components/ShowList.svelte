<script context="module" lang="ts">
    export interface Show {
        name: string;
        lineup: string[];
        admission: number;
        date: string;
        location: string;
        flyer: string | null;
    }
</script>

<script lang="ts">
    export let title: string;
    export let shows: Show[] = [];

    const formatDate = (dateStr: string): string => {
        const date = new Date(dateStr);
        return new Intl.DateTimeFormat('en-US', {
            weekday: 'short',
            year: 'numeric',
            month: 'short',
            day: 'numeric',
            hour: 'numeric',
            minute: '2-digit',
        }).format(date);
    };
</script>

<section style="width: 100%;">
    <h2 class="section-title">{title}</h2>

    {#if shows.length}
        {#each shows as {name, lineup, admission, date, location, flyer}}
            <article>
                <h3 class="show-title">{name}</h3>
                <div class="show-info">
                    {#if flyer != null}
                        <img class="show-image" alt="Flyer for {name}" src={"/flyers/" + flyer}>
                    {/if}
                    <div class={"show-description" + ( flyer == null ? " noflyer" : "" )}>
                        <p>{lineup.join(", ")}</p>
                        <p>
                            {formatDate(date)}
                            <br>
                            {location}
                        </p>
                        <p>Admission: ${admission}</p>
                    </div>
                </div>
            </article>
        {/each}
    {:else}
        <p>No {title.toLowerCase()} for now...</p>
    {/if}
</section>

<style>
    article {
        margin: 1em 0 2.5em 0;
    }

    .section-title {
        text-align: center;
    }

    .show-title {
        text-align: center;
    }

    .show-info {
        display: flex;
        flex-direction: row;
        gap: 2%;
        justify-content: center;
    }

    .noflyer {
        text-align: center;
    }

    .show-image, .show-description {
        max-width: 49%;
    }

    @media (max-width: 768px) {
        .show-info {
            flex-direction: column;
        }

        .show-image,
        .show-description {
            max-width: 100%;
        }
    }
</style>