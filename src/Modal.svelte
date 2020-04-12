<script>
  let displayModal = true;
  let isPromo = true;
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
  <div class="backdrop" class:promo={isPromo}>
    <div class="modal">
      <p>A Modal to show Offers!!</p>
    </div>
  </div>
{/if}
