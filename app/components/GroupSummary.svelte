<stackLayout class="groupPanel">
    <image 
        src={thumbnail}
        class="groupThumbnail"
    >
        {thumbnail}
    </image>
    <label for=""
        textWrap={true}
        class="groupLabel"
    >
        {name}
    </label>
</stackLayout>   

<script>
    export let name, thumbnail;
</script>

<style>
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