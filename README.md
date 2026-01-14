<!DOCTYPE html>
<html lang="ca">
<head>// Mini-Transat Watch Plan (Configurable amb Alarma)
watchPlan: {
  html: `
    <label>⏰ Temps de Son (minuts)</label><input type="number" id="sleepMin" value="20" min="10" max="90" oninput="runAction('watchPlan')">
    <label>🔭 Temps de Vigilància (hores)</label><input type="number" id="watchHrs" value="3" min="1" max="6" oninput="runAction('watchPlan')">
    <div id="alarmControls" style="margin-top:20px;">
      <p style="font-size:0.8rem; color:var(--brand); font-weight:bold; margin-bottom: 5px;">Alarma de Cicle (Simulació):</p>
      <div id="alarmDisplay" style="text-align:center; padding:15px; border:2px solid #ccc; border-radius:6px; background:#eee;">
        <h2 id="countdownTime" style="margin:0; color:#333;">--:--</h2>
        <button id="alarmToggle" onclick="toggleAlarm()" style="margin-top:10px;">Iniciar Cicle (Son)</button>
      </div>
    </div>
  `,
  action: function() {
    let sleep = parseFloat(document.getElementById('sleepMin').value) || 20;
    let watch = parseFloat(document.getElementById('watchHrs').value) || 3;
    
    return createCard("Cicle de Vigilància Individual (Mini)", "Concentració",
      `<h3>Cicle ${watch}h Vigilància / ${sleep}min Son</h3>
       <p>Aquest patró (son polifàsic) maximitza la vigilància mentre s'obtenen micro-cicles de son reparador.</p>
       <ul>
         <li>Vigilància: ${watch} hores. S'ha de comprovar l'entorn (radar, veles, rumb) i els sistemes.</li>
         <li>Descans: ${sleep} minuts. Suficient per aconseguir son d'ona lenta.</li>
       </ul>
       <div style="background:#fff3cd; padding:8px; border-left:3px solid orange; margin-top:5px">**Recomendació:** Sempre 20 minuts o 90 minuts. Evita despertar-te a la meitat d'un cicle de son profund!</div>`);
  }
}
</head>
</html>
