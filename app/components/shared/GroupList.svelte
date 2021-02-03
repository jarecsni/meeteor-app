<stackLayout orientation="horizontal" class="groupContainer">
    {#each groups as group}
        <GroupSummary {...group} />
    {/each}
</stackLayout>

<script>
    export let groups;
    import GroupSummary from './GroupSummary.svelte';
</script>

<style>
    .groupContainer {
        height: 200;
        margin: 2;
    }
</style>