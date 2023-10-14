<script lang="ts">
  import Header from './components/Header.svelte'
  import Footer from './components/Footer.svelte'
  import Tabs from './shared/Tabs.svelte'

  // tabs
  let items: string[] = ['Current Polls', 'Add New Poll'];
  let activeItem: string = 'Current Polls';

  const tabChange = (e: Event) => {
    activeItem = e.detail;
  }
</script>

<Header />
<main>
  <Tabs {items} {activeItem} on:tabChange={tabChange}/>
  {#if activeItem === 'Current Polls'}
  <p>Poll list</p>
  {:else if activeItem === 'Add New Poll'}
  <p>New poll</p>
  {/if}
</main>
<Footer />

<style>
  main {
    max-width: 960px;
    margin: 40px auto;
  }
</style>
