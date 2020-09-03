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
</style>
