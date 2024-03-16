<script>
  const employee = {
    name: "",
    profileSummery: "",
    country: "",
    languages: [],
    remoteWork: false,
    frontendSkills: [],
  };

  const save = (e) => {
    console.table(employee);
  };
</script>

<main>
  <h1>Form Page</h1>
  <div>
    <pre>
        {JSON.stringify(employee, null, 2)}
    </pre>
  </div>
  <fieldset style="width: 400px; margin:auto;">
    <legend>Job Requirements</legend>
    <form action="#">
      <div>
        <label for="name">Name</label>
        <input type="text" name="name" id="name" bind:value={employee.name} />
      </div>
      <br />
      <div>
        <label for="profile">Profile</label>
        <textarea
          type="text"
          name="profile"
          id="profile"
          bind:value={employee.profileSummery}
        ></textarea>
      </div>
      <br />
      <div>
        <label for="country">Country</label>
        <select id="country" bind:value={employee.country}>
          <option value="">Select a country</option>
          <option value="Bangladesh">Bangladesh</option>
          <option value="Pakistan">Pakistan</option>
          <option value="Bhutan">Bhutan</option>
          <option value="Nepal">Nepal</option>
        </select>
      </div>
      <br />
      <div>
        <label for="languages">Languages</label>
        <select id="languages" multiple bind:value={employee.languages}>
          <option value="Java">Java</option>
          <option value="JavaScript">JavaScript</option>
          <option value="Python">Python</option>
          <option value="C#">C#</option>
        </select>
      </div>
      <br />
      <!-- Second Part -->
      <div>
        <input
          type="checkbox"
          name="remote"
          id="remote"
          bind:checked={employee.remoteWork}
        />
        <label for="remote">Can work remotely!</label>
      </div>
      <br />
      <div>
        <label for="frontendSkills">Frontend Skills</label>
        <br />
        <input type="checkbox" name="html" id="html" />
        <label for="html">Html</label>
        <input type="checkbox" name="css" id="css" />
        <label for="css">Css</label>
        <input type="checkbox" name="js" id="js" />
        <label for="js">JS</label>
        <input type="checkbox" name="svelte" id="svelte" />
        <label for="svelte">Svelte</label>
      </div>
      <button on:click={save}>Save</button>
    </form>
  </fieldset>
</main>

<style>
</style>
