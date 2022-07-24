<script>
import { subscribe } from 'svelte/internal';

  import { readable, writable } from 'svelte/store';

  let ticketList = []
  var tickets = readable(ticketList);

  function handleClick() {
    ticketList = [...ticketList, (Math.random().toString(36).substring(7))]
    tickets = readable(ticketList)
  }
</script>

<main>
  {#each $tickets as $ticket}
    <p>{$ticket}</p>
  {/each}
  <button on:click={handleClick}>create ticket</button>
</main>
