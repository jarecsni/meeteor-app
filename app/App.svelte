<page>
    <actionBar title="Meeteor" />
    <bottomNavigation>
    <tabStrip>
        <tabStripItem title="Explorer" class="page-tab"/>
        <tabStripItem title="Home" class="page-tab"/>
        <tabStripItem title="Alerts" class="page-tab"/>
    </tabStrip>
    <tabContentItem>
        <ExplorerPage />
    </tabContentItem>
    <tabContentItem>
        <HomePage />
    </tabContentItem>
    <tabContentItem>
        <AlertsPage />
    </tabContentItem>
    </bottomNavigation>
</page>

<script>
    import ExplorerPage from './components/pages/Explorer.svelte'
    import HomePage from './components/pages/Home.svelte'
    import AlertsPage from './components/pages/Alerts.svelte'
</script>

<style>
    .page-tab {
        font-size: 13;
    }
</style>