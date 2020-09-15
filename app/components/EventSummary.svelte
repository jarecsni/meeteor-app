<label class="eventLabel">{date}</label>
<label class="eventLabel">{time}</label>
<label class="eventLabel">{title}</label>
<label class="eventLabel last">{group}</label>

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