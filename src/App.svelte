<script> 
	const AbilityScoretoModifier = (score) => {
		let Score = parseInt(score)
		if (Score<1){0}
		else if (Score<=1){return -5}
		else if (Score<=3){return -4}
		else if (Score<=5){return -3}
		else if (Score<=7){return -2}
		else if (Score<=9){return -1}
		else if (Score<=11){return 0}
		else if (Score<=13){return 1}
		else if (Score<=15){return 2}
		else if (Score<=17){return 3}
		else if (Score<=19){return 4}
		else if (Score<=21){return 5}
		else if (Score<=23){return 6}
		else if (Score<=25){return 7}
		else if (Score<=27){return 8}
		else if (Score<=29){return 9}
		else if (Score<=30){return 10}
		else if (Score>30){return 0}
	}
	let StrScore=''
	let DexScore=''
	let ConScore=''
	let IntScore=''
	let WisScore=''
	let ChaScore=''
	$: StrMod = AbilityScoretoModifier(StrScore)
	$: DexMod = AbilityScoretoModifier(DexScore)
	$: ConMod = AbilityScoretoModifier(ConScore)
	$: IntMod = AbilityScoretoModifier(IntScore)
	$: WisMod = AbilityScoretoModifier(WisScore)
	$: ChaMod = AbilityScoretoModifier(ChaScore)
	let ProfBonus=3
	$: Athletics=ProfBonus+StrMod
	$: Acrobatics=ProfBonus+DexMod
	$: Arcana=ProfBonus+IntMod

</script>
<div>
	<header>Str Calculator</header>
	<input placeholder='Str Score' bind:value={StrScore}/>
	<p>Your Str is {StrScore ? parseInt(StrScore) : 0}</p>
	<p>Your Str Mod is {StrMod > 0 ? '+' : ''}{StrMod ? StrMod : 0}</p>
	<p>Your Proficiency Bonus is +{ProfBonus}</p>
	<p>Your Athletics is {Athletics > 0 ? '+' : ''}{Athletics ? Athletics : 0}</p>
</div>
<div>
	<header>Dex Calculator</header>
	<input placeholder='Dex Score' bind:value={DexScore}/>
	<p>Your Dex is {DexScore ? parseInt(DexScore) : 0}</p>
	<p>Your Dex Mod is {DexMod > 0 ? '+' : ''}{DexMod ? DexMod : 0}</p>
	<p>Your Proficiency Bonus is +{ProfBonus}</p>
	<p>Your Acrobatics is {Acrobatics > 0 ? '+' : ''}{Acrobatics ? Acrobatics : 0}</p>
</div>
Cat