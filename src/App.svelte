<!-- add keys to the title info each statement -->
<script>
  import './Titlebar.svelte'
  import Titlebar from './Titlebar.svelte';
  const AbilityScoretoModifier = (score) => {
    let result = Math.ceil((parseInt(score) - 11) / 2);
    if (result === -0) {
      result = 0;
    }
    return result;
  };
  let CharacterName = "";
  let CharacterLevel = "";
  let StrScore = "";
  let DexScore = "";
  let ConScore = "";
  let IntScore = "";
  let WisScore = "";
  let ChaScore = "";
  $: StrMod = AbilityScoretoModifier(StrScore);
  $: DexMod = AbilityScoretoModifier(DexScore);
  $: ConMod = AbilityScoretoModifier(ConScore);
  $: IntMod = AbilityScoretoModifier(IntScore);
  $: WisMod = AbilityScoretoModifier(WisScore);
  $: ChaMod = AbilityScoretoModifier(ChaScore);
  let ProfBonus = 3;
  $: Athletics = ProfBonus + StrMod;
  $: Acrobatics = ProfBonus + DexMod;
  $: ConSave = ProfBonus + ConMod;
  $: Arcana = ProfBonus + IntMod;
  $: Insight = ProfBonus + WisMod;
  $: Performance = ProfBonus + ChaMod;
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
    <Titlebar/>
        <div class="border sizeFull">
      {@html "<!--Body-->"}
      <div class="border">
        {@html "<!--Ability Score Calculators-->"}

        <div class="border">
          {@html "<!--Strength Score Calculator-->"}
          <header class="border">Strength</header>
          <input placeholder="Str Score" bind:value={StrScore} />
          <p>Your Str is {StrScore ? parseInt(StrScore) : 0}</p>
          <p>Your Str Mod is {StrMod > 0 ? "+" : ""}{StrMod ? StrMod : 0}</p>
          <p>Your Proficiency Bonus is +{ProfBonus}</p>
          <p>
            Your Athletics is {Athletics > 0 ? "+" : ""}{Athletics
              ? Athletics
              : 0}
          </p>
        </div>
        <div class="border">
          {@html "<!--Dexterity Score Calculator-->"}
          <header class="border">Dexterity</header>
          <input placeholder="Dex Score" bind:value={DexScore} />
          <p>Your Dex is {DexScore ? parseInt(DexScore) : 0}</p>
          <p>Your Dex Mod is {DexMod > 0 ? "+" : ""}{DexMod ? DexMod : 0}</p>
          <p>Your Proficiency Bonus is +{ProfBonus}</p>
          <p>
            Your Acrobatics is {Acrobatics > 0 ? "+" : ""}{Acrobatics
              ? Acrobatics
              : 0}
          </p>
        </div>
        <div class="border">
          {@html "<!--Constitution Score Calculator-->"}
          <header class="border">Constitution</header>
          <input placeholder="Con Score" bind:value={ConScore} />
          <p>Your Con is {ConScore ? parseInt(ConScore) : 0}</p>
          <p>Your Con Mod is {ConMod > 0 ? "+" : ""}{ConMod ? DexMod : 0}</p>
          <p>Your Proficiency Bonus is +{ProfBonus}</p>
          <p>
            Your Con Save is {ConSave > 0 ? "+" : ""}{ConSave ? ConSave : 0}
          </p>
        </div>
        <div class="border">
          {@html "<!--Intelligence Score Calculator-->"}
          <header class="border">Intelligence</header>
          <input placeholder="Int Score" bind:value={IntScore} />
          <p>Your Int is {IntScore ? parseInt(IntScore) : 0}</p>
          <p>Your Int Mod is {IntMod > 0 ? "+" : ""}{IntMod ? IntMod : 0}</p>
          <p>Your Proficiency Bonus is +{ProfBonus}</p>
          <p>Your Arcana is {Arcana > 0 ? "+" : ""}{Arcana ? Arcana : 0}</p>
        </div>
        <div class="border">
          {@html "<!--Wisdom Score Calculator-->"}
          <header class="border">Wisdom</header>
          <input placeholder="Wis Score" bind:value={WisScore} />
          <p>Your Wis is {WisScore ? parseInt(WisScore) : 0}</p>
          <p>Your Wis Mod is {WisMod > 0 ? "+" : ""}{WisMod ? WisMod : 0}</p>
          <p>Your Proficiency Bonus is +{ProfBonus}</p>
          <p>Your Insight is {Insight > 0 ? "+" : ""}{Insight ? Insight : 0}</p>
        </div>
        <div class="border">
          {@html "<!--Charisma Score Calculator-->"}
          <header class="border">Charisma</header>
          <input placeholder="Cha Score" bind:value={ChaScore} />
          <p>Your Cha is {ChaScore ? parseInt(IntScore) : 0}</p>
          <p>Your Cha Mod is {ChaMod > 0 ? "+" : ""}{ChaMod ? ChaMod : 0}</p>
          <p>Your Proficiency Bonus is +{ProfBonus}</p>
          <p>
            Your Performance is {Performance > 0 ? "+" : ""}{Performance
              ? Performance
              : 0}
          </p>
        </div>
      </div>
    </div>
  </div>
  <style>
  </style>
</body>
