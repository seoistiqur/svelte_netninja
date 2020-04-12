<script>
  let people = [
    { name: "Naruto", beltColor: "Orange", age: 15, id: 1 },
    { name: "Jiraiya", beltColor: "Red", age: 55, id: 2 },
    { name: "Tsunade", beltColor: "Pink", age: 45, id: 3 }
  ];
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 2em;
    font-weight: 100;
  }

  h5 {
    color: royalblue;
    text-transform: lowercase;
    font-size: 1.5em;
  }

  button {
    color: black;
    background-color: tomato;
    font-family: cursive;
    padding: 10px;
    font-size: 15px;
    font-weight: bolder;
    border-radius: 20%;
    -moz-box-shadow: inset 0 0 15px #000000;
    -webkit-box-shadow: inset 0 0 15px #000000;
    box-shadow: inset 0 0 15px #000000;
  }

  button:hover {
    -webkit-box-shadow: 0 8px 6px -6px black;
    -moz-box-shadow: 0 8px 6px -6px black;
    box-shadow: 0 8px 6px -6px black;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
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

<main>
  {#each people as person (person.id)}
    <div style="margin-bottom: 50px;">
      <h1>Here, this is {person.name}.</h1>
      <h5>The ninja is {person.age} years old.</h5>
      <h6>Corrspondent belt color is {person.beltColor}.</h6>
      <hr />
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
  <!-- <input type="text" on:input={handleInput} value={name} /> -->
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
