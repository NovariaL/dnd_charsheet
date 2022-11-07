<script>
  const AbilityScoretoModifier = (score) => {
    let result = Math.ceil((parseInt(score) - 11) / 2);
    if (result === -0) {
      result = 0;
    }
    return result;
  };
  let CharacterName = "";
  let CharacterLevel = "";
</script>
<head>
  <style>
    .flex-container {
      display: flex;
      background-color: white;
    }
    .flex-containerCentered {
      display: flex;
      background-color: white;
      justify-content: space-evenly;
    }
    .flex-container > div {
      background-color: #fff;
      margin: 10px;
      padding: 5%;
      font-size: 20px;
    }
    .border {
      border: 2px solid black;
      padding: 1%;
      margin: 5px;
      border-radius: 10px;
    }
    .sizeFull {
      height: 100%;
      width: 100%;
    }
    .Title {
      margin: 10px;
    }
    div {
      color: black;
      font-family: Calibri;
    }
    input {
      background-color: lightgrey;
      text-align: center;
      color: black;
      font-family: Calibri;
      font-size: 1em;
      width: 80%;
      margin: 0 5px;
      padding: 5px;
    }
    head {
      height: 100%;
      width: 100%;
    }
    body {
      background-color: white;
      margin: 0px;
      height: 100%;
      width: 100%;
    }
    p {
      font-size: 20px;
    }
    header {
      font-size: 40px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="sizeFull">
    {@html "<!--Main-->"}
    <header class="Title">Interactive Character Sheet</header>
    <div class="border sizeFull flex-container">
      {@html "<!--Title Bar-->"}
      <style>
      </style>

      <div class="border">
        {@html "<!--Character Name-->"}
        <input placeholder="Character Name" bind:value={CharacterName} />
        <p>Character Name</p>
      </div>
      <div class="border">
        {@html "<!--Character Info & Player Name-->"}
        <div>
          <div>
            <input />
            <p>Class</p>
          </div>
          <div>
            <input />
            <p>Level</p>
          </div>
          <div>
            <input />
            <p>Background</p>
          </div>
          <div>
            <input />
            <p>Player Name</p>
          </div>
        </div>
        <div>
          <div>
            <input />
            <p>Race</p>
          </div>
          <div>
            <input />
            <p>Alignment</p>
          </div>
          <div>
            <input />
            <p>Experience Points</p>
          </div>
        </div>
      </div>
      <div class=" flex-containerCentered">
        <input />
        <p />
      </div>
    </div>
  </div>
</body>
