<script>
  // Some Event Modifiers
  // Once ->event can only fire once (removes handler).
  // precentDefault ->precent default action (e.preventDefault).
  // self -> only fires ifclicked on self.

  // export let message;
  //   let message = "not prop";
  export let displayModal = false;
  //   export let isPromo = false;
  export let isPromo = true;
</script>

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.97);
  }

  .modal {
    color: whitesmoke;
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    text-align: center;
    background: rgba(255, 255, 255, 0.44);
  }

  .promo .modal {
    background: maroon;
  }
</style>

{#if displayModal}
  <!-- a blank on:click isforwarding event to the parent component -->
  <!-- <div class="backdrop" class:promo={isPromo}>
    <div class="modal">
      <p on:click>{message}</p>
    </div>
  </div> -->
  <!-- <div class="backdrop" class:promo={isPromo} on:click>
    <div class="modal">
      <p>{message}</p>
    </div>
  </div> -->
  <!-- on:click|self means "self event modifier" -->
  <!-- <div class="backdrop" class:promo={isPromo} on:click|self>
    <div class="modal">
      <p>{message}</p>
      <slot></slot>
      <slot name="title"></slot>
      <slot></slot>
    </div>
  </div> --> 

  <div class="backdrop" class:promo={isPromo} on:click|self>
    <div class="modal">
      <slot></slot>
    </div>
  </div>
{/if}
