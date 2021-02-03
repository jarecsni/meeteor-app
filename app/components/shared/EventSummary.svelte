<label for="" class="eventLabel">{date}</label>
<label for="" class="eventLabel">{time}</label>
<label for="" class="eventLabel">{title}</label>
<label for="" class="eventLabel last">{group}</label>

<script>
    export let date, time, title, group;
</script>

<style>
    .eventLabel {
        margin-left: 10;
    }
    .eventLabel.last {
        margin-bottom: 10;
    }
</style>