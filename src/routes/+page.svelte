<script lang="ts">
    import shows from "$lib/data/shows.json";
    import ShowList, { type Show } from "$lib/components/ShowList.svelte";

    const currentDate = new Date();
    let upcomingShows:Show[] = [];
    let pastShows:Show[] = [];

    shows.forEach((show) => {
        if (new Date(show.date) >= currentDate) {
            upcomingShows.push(show);
        } else {
            pastShows.push(show);
        }
    });

    upcomingShows.sort((a, b) => new Date(a.date).getTime() - new Date(b.date).getTime());
    pastShows.sort((a, b) => new Date(b.date).getTime() - new Date(a.date).getTime());

</script>

<ShowList title="Upcoming Shows" shows={upcomingShows} />
<ShowList title="Past Shows" shows={pastShows} />
