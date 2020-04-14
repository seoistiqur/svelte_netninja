<script>
  import Modal from "./Modal.svelte";
  import Form from "./Form.svelte";

  let displayModal = false;
  const toggleModal = () => {
    displayModal = !displayModal;
  };

  let people = [
    { name: "Naruto", beltColor: "Orange", age: 15, id: 1 },
    { name: "Jiraiya", beltColor: "Red", age: 55, id: 2 },
    { name: "Tsunade", beltColor: "Pink", age: 45, id: 3 }
  ];

  const handleDelete = id => {
    people = people.filter(person => person.id !== id);
  };

  let num = 5;
</script>

<style>
  h1 {
    color: orangered;
    display: block;
    font-family: sans-serif;
  }

  h5 {
    color: darkorange;
    display: block;
    font-family: serif;
  }

  h4 {
    color: navy;
    display: block;
    font-family: monospace;
  }

  button {
    box-shadow: inset 0 0 10px #000000;
  }

  button:hover {
    box-shadow: 0 8px 6px -6px black;
  }
</style>


<Modal
  isPromo={true}
  {displayModal}
  on:click={toggleModal}>
<Form />
</Modal>


<main>
 
  <button on:click={toggleModal}>Open Modal</button>
  {#each people as person (person.id)}
    <div>
      <h1>Here, this is {person.name}.</h1>
      {#if person.beltColor === 'Red'}
        <p>
          <em>Master Man!</em>
        </p>
      {:else}
        <p>
          <b>Other</b>
        </p>
      {/if}
      <h5>The ninja is {person.age} years old.</h5>
      <h4>Corrspondent belt color is {person.beltColor}.</h4>
      <button
        on:click={() => {
          handleDelete(person.id);
        }}>
        Delete
      </button>
    </div>
  {:else}
    <p>No people to show...</p>
  {/each}
</main>
