<script>
    import Header from "./components/Header.svelte";
    import Footer from "./components/Footer.svelte";
    import Tabs from "./shared/Tabs.svelte";

    //    tabs
    let items = ['Current Polls', 'Add New Poll'];
    let activeItem = 'Current Polls';
</script>

<Header />
<main>
    <Tabs {items} {activeItem} on:tabSelected={(e) => activeItem = e.detail} />
    {#if activeItem === 'Current Polls'}
        <p>Poll list component goes here</p>
    {:else if activeItem === 'Add New Poll'}
        <p>New Poll form Component goes here</p>
    {/if}

</main>

<Footer />
<style>
    main {
        max-width: 960px;
        margin: 40px auto;
    }
</style>
