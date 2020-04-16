<!-- <script>
	let name;
	let beltColor;
	let age;
	let ninjutsu = false;
	let genjutsu = false;
	let taijutsu = false;

	const handleSubmit = () => {
		console.log(name, beltColor, age, ninjutsu, genjutsu, taijutsu);
	}
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="belt color" bind:value={beltColor} />
  <input type="number" placeholder="age" bind:value={age} />
  <label>Skills</label>
  <input type="checkbox" bind:checked={ninjutsu}>ninjutsu<br />
  <input type="checkbox" bind:checked={genjutsu}>genjutsu<br />
  <input type="checkbox" bind:checked={taijutsu}>taijutsu<br />
  <button>Add Person</button>
</form>

 -->

 <script>
	let name;
	let beltColor;
	let age;
	let skills = [];
	let gender;

	const handleSubmit = () => {
		console.log(name, beltColor, age, skills, gender);
	}
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

