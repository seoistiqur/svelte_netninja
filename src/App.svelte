<script>
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
  main {
    margin: 25px;
    padding: 25px;
  }

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

<!-- <main>
  <div>
    <h4>{people[0].name}</h4>
    <p>{people[0].beltColor}</p>
    <p>{people[0].age}</p>
  </div>
  <div>
    <h4>{people[1].name}</h4>
    <p>{people[1].beltColor}</p>
    <p>{people[1].age}</p>
  </div>
  <div>
    <h4>{people[2].name}</h4>
    <p>{people[2].beltColor}</p>
    <p>{people[2].age}</p>
  </div>
</main> -->

<!-- {#if num > 20}
<p>Greater than 20.</p>
{:else if num > 5}
<p>Greater than 5.</p>
{:else}
<p>Neither</p>
{/if} -->

<main>
  {#each people as person (person.id)}
    <div>
      <h1>Here, this is {person.name}.</h1>
      {#if person.beltColor === 'Red'}
        <p>
          <em>Master Man!</em>
        </p>
      {:else}
        <p>
          <b>Others</b>
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

<!-- <script>
  //   let name = "Rabby";
  let firstName = "Istiqur";
  let lastName = "Rahman";
  //   let profession = "Frontend Developer";
  let color = "blue";

  // Reactive value
  $: fullName = `${firstName} ${lastName}`;
  // Reactive statement
  //   $: console.log(color);
  //   $: {
  //     console.log(firstName);
  //     console.log(color);
  //     console.log(lastName);
  //     console.log(fullName);
  //   }

  const handleClick = () => {
    // name = "Istiqur";
    color = "black";
  };

  const handleInput = e => {
    color = e.target.value;
  };
</script> -->

<!-- <main>
  <h1>Meet {name} :)</h1>
  <h3 style="color: {color}">He likes the color {color}</h3>
  <button on:click={handleClick}>Update Name</button>
   <input type="text" on:input={handleInput} value={name} /> -->
<!-- <input type="text" on:input={handleInput} /> -->
<!-- <input type="text" bind:value={color} />
</main> -->
<!-- <main>
  <h3>{fullName} likes the color {color}</h3> -->
<!-- <h3>{firstName} {lastName} likes the color {color}</h3> -->
<!-- <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <input type="text" bind:value={color} />
</main> -->
