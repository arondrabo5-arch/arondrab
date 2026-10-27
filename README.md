 arondrab
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
const card=document
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#080808">
  <title>ARON73 VIP PRONOS</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      background: #080808;
      color: white;
      font-family: Arial, sans-serif;
    }
    header {
      background: linear-gradient(135deg, #151515, #29200b);
      border-bottom: 2px solid #d4af37;
      padding: 25px 15px;
      text-align: center;
    }
    h1 { color: #e5c34b; margin: 0; font-size: 27px; }
    header p { color: #ddd; }
    main { max-width: 700px; margin: auto; padding: 16px; }
    .card {
      background: #171717;
      border: 1px solid #66531c;
      border-radius: 12px;
      padding: 18px;
      margin: 16px 0;
    }
    h2 { color: #e5c34b; font-size: 20px; }
    label { display: block; margin: 12px 0 6px; }
    input, select, textarea {
      width: 100%;
      padding: 12px;
      border-radius: 7px;
      border: 1px solid #777;
      background: #090909;
      color: white;
      font-size: 16px;
    }
    button {
      width: 100%;
      padding: 13px;
      margin-top: 12px;
      background: #d4af37;
      color: #111;
      font-weight: bold;
      border: 0;
      border-radius: 7px;
      font-size: 16px;
      cursor: pointer;
    }
    .result { white-space: pre-wrap; line-height: 1.7; }
    .muted { color: #bbb; font-size: 13px; }
    footer { text-align: center; padding: 25px; color: #aaa; }
  </style>
</head>
<body>
  <header>
    <h1>ARON73 VIP PRONOS</h1>
    <p>⚽ Analyse • Pronostics • Football</p>
  </header>

  <main>
    <section class="card">
      <h2>Bienvenue !</h2>
      <p>Retrouve tes analyses de matchs et prépare tes pronostics.</p>
      <p class="muted">Les pronostics sont des estimations, jamais des résultats garantis.</p>
    </section>

    <section class="card">
      <h2>⚽ Préparer une analyse</h2>
      <label for="match">Match</label>
      <input id="match" placeholder="Ex. Real Madrid - Barcelone">

      <label for="competition">Compétition</label>
      <input id="competition" placeholder="Ex. Liga">

      <label for="forme">Forme des équipes</label>
      <textarea id="forme" rows="3" placeholder="Derniers résultats, absents, statistiques..."></textarea>

      <button onclick="generer()">Préparer mon analyse</button>
    </section>

    <section class="card" id="zoneResultat" hidden>
      <h2>📊 Fiche de pronostic</h2>
      <div id="resultat" class="result"></div>
      <button onclick="copierAnalyse()">Copier la fiche</button>
    </section>

    <section class="card">
      <h2>📌 Nos conseils</h2>
      <p>• Vérifie les compositions officielles.</p>
      <p>• Compare les statistiques récentes.</p>
      <p>• Ne mise jamais de l'argent nécessaire aux dépenses essentielles.</p>
    </section>
  </main>

  <footer>© 2026 ARON73 VIP PRONOS</footer>

  <script>
    function generer() {
      const match = document.getElementById('match').value.trim();
      const competition = document.getElementById('competition').value.trim();
      const forme = document.getElementById('forme').value.trim();

      if (!match) {
        alert('Entre le nom du match avant de continuer.');
        return;
      }

      const texte =
        'ARON73 VIP PRONOS\n\n' +
        'Match : ' + match + '\n' +
        'Compétition : ' + (competition || 'Non précisée') + '\n\n' +
        'Informations disponibles :\n' +
        (forme || 'Aucune statistique ajoutée.') + '\n\n' +
        'À vérifier avant tout pronostic :\n' +
        '1. Forme récente\n' +
        '2. Attaque, milieu et défense\n' +
        '3. Corners et buts\n' +
        '4. Absences et compositions\n\n' +
        'Les données saisies ne suffisent pas à établir un pronostic fiable. ' +
        'Fais vérifier les statistiques avant de choisir un pari.';

      document.getElementById('resultat').textContent = texte;
      document.getElementById('zoneResultat').hidden = false;
    }

    async function copierAnalyse() {
      const texte = document.getElementById('resultat').textContent;
      try {
        await navigator.clipboard.writeText(texte);
        alert('Fiche copiée !');
      } catch (e) {
        alert('Sélectionne le texte de la fiche pour le copier.');
      }
    }
  </script>
</body>
</html>

