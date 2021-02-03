<page>
    <stackLayout>
        <label for="" class="header">Your Groups</label>
        <scrollView orientation="horizontal" scrollbarIndicatorVisible={false}>
            <GroupList groups={myGroups} />
        </scrollView>
        <label for="" class="header">Your Calendar</label>
        <segmentedBar class="calendar"
            selectedIndex={currentCalendar}
            on:selectedIndexChange={onCalendarTypeChange}
        >
            <segmentedBarItem title="Your Groups"/>
            <segmentedBarItem title="Going"/>
            <segmentedBarItem title="Past Events"/>
        </segmentedBar>
        {#if currentCalendar === 0}
            <EventList events={upcomingEvents}/>
        {:else if currentCalendar === 1}
            <label for="" margin=10>Events you booked</label>
        {:else}
            <label for="" margin=10>Past events</label>
        {/if}

    </stackLayout>
</page>

<script>
    import EventList from '../shared/EventList.svelte';
    import GroupList from '../shared/GroupList.svelte';
    const myGroups = [
        {
            name: 'Sunday Book Club',
            thumbnail: 'https://bookofaces.files.wordpress.com/2019/02/ck-jhbsun081fshcr.jpg?w=256&h=256&crop=1'
        },
        {
            name: 'Svelte Natives',
            thumbnail: 'https://twobluecommunications.com/wp-content/uploads/2018/12/Chelsea-Waterfront-3-256x256.jpg'
        },
        {
            name: 'Svelte Stars',
            thumbnail: 'https://twobluecommunications.com/wp-content/uploads/2018/06/Eastward-view-cropped-bottom-downsized-256x256.jpg'
        },
        {
            name: 'Svelte Life',
            thumbnail: 'https://twobluecommunications.com/wp-content/uploads/2018/06/Eastward-view-cropped-bottom-downsized-256x256.jpg'
        }
    ];

    let currentCalendar = 0;
    function onCalendarTypeChange(e) {
        currentCalendar = e.value;
    }

    let upcomingEvents = [
        {
            date: '18/06/2020',
            time: '16:00',
            title: 'Some interesting event',
            group: 'React London'
        },
        {
            date: '18/06/2020',
            time: '18:00',
            title: 'Why Svelte is the Best?',
            group: 'Svelte Hackers'
        },
        {
            date: '19/06/2020',
            time: '18:00',
            title: 'Templating with Svelte',
            group: 'Svelte Rookies'
        }
    ];
    
</script>

<style>
    .header {
        font-size: 24;
        margin: 10;
    }
    .calendar {
        margin: 5;
        color: white;
    }
    .calendar {
        margin: 5;
        color: white;
    }
</style>
