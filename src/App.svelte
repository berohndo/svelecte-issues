<script>
  import Svelecte from "svelecte";

  const optionsShared = [
    { id: 1, label: "Option 1" },
    { id: 2, label: "Option 2" },
    { id: 3, label: "Option 3" },
  ];

  const optionsNonShared = [
    { id: 1, label: "Option 1" },
    { id: 2, label: "Option 2" },
    { id: 3, label: "Option 3" },
  ];

  let selectionFirst = null;
  let selectionSecond = null;

  let selectionThird = null;
  let selectionFourth = null;
</script>

<main>
  <h1>Not working (shared options)</h1>
  <small
    ><ol>
      <li>set option 1, 2 and 3 in first selectbox</li>
      <li>
        try to set option 1, 2 and 3 in second selectbox - but after selection
        of option 1, no other option is available anymore
      </li>
    </ol></small
  >

  <div>
    <Svelecte
      options={optionsShared}
      bind:selection={selectionFirst}
      multiple
    />
  </div>
  <div>
    <Svelecte
      options={optionsShared}
      bind:selection={selectionSecond}
      multiple
    />
  </div>

  <h1>Working (non shared options)</h1>
  <div>
    <Svelecte
      options={optionsNonShared.map((o) => ({ id: o.id, label: o.label }))}
      bind:selection={selectionThird}
      multiple
    />
  </div>

  <div>
    <Svelecte
      options={optionsNonShared.map((o) => ({ id: o.id, label: o.label }))}
      bind:selection={selectionFourth}
      multiple
    />
  </div>
</main>

<style>
  div {
    width: 400px;
    margin: 20px;
  }
</style>
