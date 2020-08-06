<script>
    import PollStore from '../stores/PollStore';
    import PollDetails from './PollDetails.svelte';
    // import { onMount, onDestroy } from 'svelte';

    // export let polls = [];

    // const unsub = PollStore.subscribe(data => {
    //     polls = data;
    // });

    // onDestroy(() => {
    //     // unsub from store
    //     console.log('component destroyed');
    //     unsub();
    // })

</script>

<div class="poll-list">
    {#each $PollStore as poll (poll.id)}
        <div><PollDetails {poll} on:vote /></div>
    {/each}
</div>

<style>
    .poll-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }
</style>