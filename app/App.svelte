<page>
    <actionBar title="Meeteor" />
    <stackLayout>
        <label class="header">Your Groups</label>
        <scrollView orientation="horizontal" scrollbarIndicatorVisible={false}>
            <stackLayout orientation="horizontal" class="groupContainer">
                {#each myGroups as group}
                    <stackLayout class="groupPanel">
                        <image 
                            src={group.thumbnail}
                            class="groupThumbnail"
                        >
                            {group.thumbnail}
                        </image>
                        <label
                            textWrap={true}
                            class="groupLabel"
                        >
                            {group.name}
                        </label>
                    </stackLayout>
                {/each}
            </stackLayout>
        </scrollView>
        <label class="header">Your Calendar</label>
        <segmentedBar class="calendar"
            selectedIndex={currentCalendar}
            on:selectedIndexChange={onCalendarTypeChange}
        >
            <segmentedBarItem title="Your Groups"/>
            <segmentedBarItem title="Going"/>
            <segmentedBarItem title="Past Events"/>
        </segmentedBar>
        {#if currentCalendar === 0}
            <scrollView scrollbarIndicatorVisible={false}>
                <stackLayout>
                    {#each upcomingEvents as event}
                        <label class="eventLabel">{event.date}</label>
                        <label class="eventLabel">{event.time}</label>
                        <label class="eventLabel">{event.title}</label>
                        <label class="eventLabel last">{event.group}</label>
                    {/each}
                </stackLayout>
            </scrollView>
        {:else if currentCalendar === 1}
            <label margin=10>Events you booked</label>
        {:else}
            <label margin=10>Past events</label>
        {/if}

    </stackLayout>
</page>

<script>
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
    .groupContainer {
        height: 200;
        margin: 2;
    }
    .groupPanel {
        background-color: lightgray;
        margin: 4;
    }
    .groupThumbnail {
        width: 100;
    }
    .groupLabel {
        margin-left: 4;
        width: 100;
        height: 50;
    }
    .calendar {
        margin: 5;
        color: white;
    }
    .eventLabel {
        margin-left: 10;
    }
    .eventLabel.last {
        margin-bottom: 10;
    }
</style>
