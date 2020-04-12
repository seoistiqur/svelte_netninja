<script>
  let name = "Rabby";
  let profession = "Frontend Developer";
  let color = "blue";

  const handleClick = () => {
	// name = "Istiqur";
	color = "black";
  };

  const handleInput = e => {
    color = e.target.value;
  };
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
    font-size: 4em;
    font-weight: 100;
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

<main>
  <h1>Meet {name} :)</h1>
  <h3 style="color: {color}">He likes the color {color}</h3>
  <button on:click={handleClick}>Update Name</button>
  <!-- <input type="text" on:input={handleInput} value={name} /> -->
  <!-- <input type="text" on:input={handleInput} /> -->
  <input type="text" bind:value={color} />
</main>
