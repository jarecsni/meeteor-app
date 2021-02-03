<page>
    <actionBar title="Meeteor" />
    <bottomNavigation>
    <tabStrip>
        <tabStripItem title="Explorer"/>
        <tabStripItem title="Home"/>
        <tabStripItem title="Alerts"/>
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

