 <script>
    import { createEventDispatcher } from "svelte";

    let dispatch = createEventDispatcher();

	let name;
	let beltColor;
	let age;
	let skills = [];
	let gender;

	const handleSubmit = () => {
		const person = {
      name,
      beltColor,
      age,
      skills,
      id: Math.random()

    };
    dispatch("addPerson", person);
	};
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="belt color" bind:value={beltColor} />
  <input type="number" placeholder="age" bind:value={age} />
  <label>Skills</label>
  <input type="checkbox" bind:group={skills} value="ninjutsu">ninjutsu<br />
  <input type="checkbox" bind:group={skills} value="genjutsu">genjutsu<br />
  <input type="checkbox" bind:group={skills} value="taijutsu">taijutsu<br />
  <label>Gender</label>
  <select bind:value={gender}>
  	<option value="male">male</option>
  	<option value="female">female</option>
  	<option value="not relevant">not relevant</option>
  </select>
  <button>Add Person</button>
</form>

