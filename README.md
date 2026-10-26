# arondrab
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>ARON73 VIP PRONOS</title>
<style>
body{margin:0;background:#090909;color:white;font-family:Arial,sans-serif}
header{text-align:center;padding:25px 10px;border-bottom:2px solid #f2c14e}
h1,h2{color:#f2c14e}
main{padding:16px;max-width:700px;margin:auto}
.card{background:#191919;padding:16px;border-radius:12px;margin:14px 0}
button{background:#f2c14e;color:#111;border:0;border-radius:8px;padding:12px;font-weight:bold;margin:4px}
input,select,textarea{box-sizing:border-box;width:100%;padding:12px;margin:6px 0;background:#080808;color:white;border:1px solid #555;border-radius:7px}
label{display:block;margin-top:10px;color:#ddd}
.note{color:#ccc;font-size:13px;line-height:1.5}
</style>
</head>
<body>
<header>
<h1>ARON73 VIP PRONOS</h1>
<p>⚽ Analyses • Scores • Corners • Double chance</p>
</header>
<main>
<div class="card">
<h2>Bienvenue</h2>
<p>Prépare tes analyses de matchs avec ARON73 VIP PRONOS.</p>
<p class="note">Les exemples ne sont pas des pronostics en direct. Aucun score ni gain n'est garanti.</p>
</div>

<div class="card">
<h2>Ajouter un match</h2>
<label>Équipe à domicile</label>
<input id="home" placeholder="Ex : Real Madrid">
<label>Équipe adverse</label>
<input id="away" placeholder="Ex : Barcelone">
<label>Compétition</label>
<input id="league" placeholder="Ex : Liga">
<label>Score principal</label>
<input id="s1" placeholder="Ex : 2-1">
<label>Score offensif 1</label>
<input id="s2" placeholder="Ex : 3-1">
<label>Score offensif 2</label>
<input id="s3" placeholder="Ex : 2-2">
<label>Double chance</label>
<select id="dc">
<option>À analyser</option>
<option>1X</option>
<option>X2</option>
<option>12</option>
</select>
<label>Analyse des corners</label>
<input id="corners" placeholder="Estimation à vérifier">
<label>Analyse générale</label>
<textarea id="analysis" rows="3" placeholder="Forme, attaque, milieu, défense, absences..."></textarea>
<button onclick="addMatch()">AJOUTER LE MATCH</button>
</div>

<div class="card">
<h2>Mes pronostics</h2>
<div id="results">
<p class="note">Tes matchs ajoutés apparaîtront ici.</p>
</div>
</div>

<div class="card">
<h2>Méthode d'analyse</h2>
<p>1. Vérifier les compositions.</p>
<p>2. Examiner l'attaque, le milieu et la défense.</p>
<p>3. Étudier la forme récente des équipes.</p>
<p>4. Vérifier les statistiques de corners.</p>
<p>5. Comparer plusieurs scores possibles.</p>
</div>
</main>

<script>
function addMatch(){
const get=id=>document.getElementById(id).value.trim();
const home=get('home'),away=get('away');
if(!home||!away){
alert('Entre les deux équipes.');
return;
}
const card=document.createElement('div');
card.className='card';
const title=document.createElement('h2');
title.textContent=home+' vs '+away;
card.appendChild(title);
[
'Compétition : '+(get('league')||'Non précisée'),
'Score principal : '+(get('s1')||'À analyser'),
'Score offensif 1 : '+(get('s2')||'À analyser'),
'Score offensif 2 : '+(get('s3')||'À analyser'),
'Double chance : '+get('dc'),
'Corners : '+(get('corners')||'À analyser'),
'Notes : '+(get('analysis')||'Aucune')
].forEach(text=>{
const p=document.createElement('p');
p.textContent=text;
card.appendChild(p);
});
const del=document.createElement('button');
del.textContent='Supprimer';
del.onclick=()=>card.remove();
card.appendChild(del);
document.getElementById('results').prepend(card);
['home','away','league','s1','s2','s3','corners','analysis'].forEach(id=>document.getElementById(id).value='');
document.getElementById('dc').selectedIndex=0;
}
</script>
</body>
</html>
