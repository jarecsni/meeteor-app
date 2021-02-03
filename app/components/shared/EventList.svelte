<scrollView scrollbarIndicatorVisible={false}>
    <stackLayout>
        {#each events as event}
            <EventSummary {...event}/>
        {/each}
    </stackLayout>
</scrollView>

<script>
    import EventSummary from './EventSummary.svelte';
    export let events;
</script>