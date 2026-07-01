<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<title>Mein Budget 2026</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --bg:#0F0F13;--bg2:#1A1A22;--bg3:rgba(255,255,255,0.04);
    --border:rgba(255,255,255,0.07);--border2:rgba(255,255,255,0.13);
    --text:#F0EDE8;--text2:#999;--text3:#666;--text4:#444;
    --green:#5C8A5C;--blue:#4A7FA5;--orange:#D4845A;--red2:#E05252;
  }
  html{scroll-behavior:smooth;-webkit-text-size-adjust:100%}
  body{background:var(--bg);color:var(--text);font-family:'DM Sans',-apple-system,sans-serif;min-height:100vh;-webkit-font-smoothing:antialiased}
  ::-webkit-scrollbar{width:3px}::-webkit-scrollbar-thumb{background:#2a2a2a;border-radius:2px}
  header{background:linear-gradient(135deg,var(--bg2),#141418);border-bottom:1px solid var(--border);padding:28px 20px 18px;padding-top:max(28px,env(safe-area-inset-top,28px));position:sticky;top:0;z-index:100}
  .hi{max-width:680px;margin:0 auto}
  .ht{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:14px}
  .lbl{font-family:'DM Mono',monospace;font-size:10px;letter-spacing:2px;color:var(--text3);text-transform:uppercase;margin-bottom:4px}
  h1{font-size:22px;font-weight:600;letter-spacing:-0.5px}
  .tabs{display:flex;gap:6px}
  .tab{padding:7px 16px;border-radius:20px;font-size:12px;font-family:'DM Sans',sans-serif;cursor:pointer;border:none;background:var(--bg3);color:var(--text2);-webkit-tap-highlight-color:transparent;transition:all 0.15s}
  .tab.active{background:var(--text);color:var(--bg);font-weight:600}
  .mnav{display:flex;align-items:center;gap:10px}
  .nb{background:rgba(255,255,255,0.07);border:none;border-radius:8px;width:32px;height:32px;color:var(--text);font-size:18px;cursor:pointer;display:flex;align-items:center;justify-content:center;-webkit-tap-highlight-color:transparent}
  .nb:active{background:rgba(255,255,255,0.15)}
  .ml{font-size:16px;font-weight:500;flex:1;text-align:center}
  main{max-width:680px;margin:0 auto;padding:18px 16px 100px}
  .sg{display:grid;grid-template-columns:1fr 1fr 1fr;gap:9px;margin-bottom:13px}
  .sc{background:var(--bg3);border:1px solid var(--border);border-radius:11px;padding:12px 13px}
  .sl{font-family:'DM Mono',monospace;font-size:9px;letter-spacing:1.5px;color:var(--text3);text-transform:uppercase;margin-bottom:5px}
  .sv{font-size:17px;font-weight:600;margin-bottom:2px;font-variant-numeric:tabular-nums}
  .ss{font-size:10px;color:var(--text3)}
  .fb{background:var(--bg3);border:1px solid var(--border);border-radius:11px;padding:11px 15px;margin-bottom:13px;display:flex;justify-content:space-between;align-items:center;gap:10px}
  .cg{display:grid;grid-template-columns:1fr 1fr;gap:9px;margin-bottom:13px}
  .cc{background:var(--bg3);border:1px solid var(--border);border-radius:13px;padding:14px;position:relative;overflow:hidden;transition:transform 0.15s,border-color 0.2s}
  .cc:active{transform:scale(0.98)}.cc.over{border-color:rgba(224,82,82,0.4)}
  .ca{position:absolute;top:0;left:0;right:0;height:2px;border-radius:13px 13px 0 0;opacity:0.65}
  .ct{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:10px}
  .ci{font-size:19px}.cn{font-size:11px;color:var(--text2);margin-top:3px;line-height:1.2}
  .cam{display:flex;align-items:baseline;gap:5px;margin-bottom:10px}
  .cs{font-size:20px;font-weight:600;font-family:'DM Mono',monospace;font-variant-numeric:tabular-nums}
  .co{font-size:11px;color:var(--text4);font-family:'DM Mono',monospace}
  .pb{height:3px;background:rgba(255,255,255,0.07);border-radius:2px;margin-bottom:11px;overflow:hidden}
  .pf{height:100%;border-radius:2px;transition:width 0.5s cubic-bezier(.4,0,.2,1)}
  .cac{display:flex;gap:5px}
  .cb{flex:1;background:rgba(255,255,255,0.06);border:none;border-radius:7px;padding:7px 0;color:var(--text2);font-size:11px;font-family:'DM Sans',sans-serif;cursor:pointer;-webkit-tap-highlight-color:transparent}
  .cb:active{background:rgba(255,255,255,0.12)}
  .ir{display:flex;gap:6px;margin-bottom:10px}
  .ii{flex:1;background:rgba(255,255,255,0.09);border:1px solid var(--border2);border-radius:7px;padding:7px 9px;color:var(--text);font-size:14px;font-family:'DM Mono',monospace;-webkit-appearance:none}
  .ii:focus{outline:none;border-color:rgba(255,255,255,0.3)}
  .io{border:none;border-radius:7px;padding:7px 13px;color:#fff;font-size:12px;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;-webkit-tap-highlight-color:transparent}
  .be{background:rgba(255,255,255,0.03);border:1px solid var(--border);border-radius:13px;padding:15px 16px}
  .bg2{display:grid;grid-template-columns:1fr 1fr;gap:9px}
  .br{display:flex;align-items:center;gap:7px}
  .bi{width:58px;background:rgba(255,255,255,0.06);border:1px solid rgba(255,255,255,0.1);border-radius:7px;padding:4px 7px;color:var(--text);font-size:12px;text-align:right;font-family:'DM Mono',monospace;-webkit-appearance:none}
  .bi:focus{outline:none;border-color:rgba(255,255,255,0.25)}
  .sb{background:rgba(74,127,165,0.1);border:1px solid rgba(74,127,165,0.25);border-radius:11px;padding:11px 15px;margin-bottom:14px;display:flex;align-items:center;gap:10px}
  .sd{width:7px;height:7px;border-radius:50%;background:#4A7FA5;flex-shrink:0;animation:pulse 2s infinite}
  @keyframes pulse{0%,100%{opacity:1}50%{opacity:0.4}}
  .hc{background:var(--bg3);border:1px solid var(--border);border-radius:12px;padding:13px 15px;margin-bottom:10px}
  .hc.over{border-color:rgba(224,82,82,0.25)}
  .hh{display:flex;justify-content:space-between;align-items:center;margin-bottom:11px}
  .hbars{display:flex;gap:3px;height:38px;align-items:flex-end;margin-bottom:5px}
  .hbar{flex:1;border-radius:3px 3px 0 0;opacity:0.75;min-height:2px}
  .hicons{display:flex;gap:3px}
  .hic{flex:1;text-align:center;font-size:10px}
  .hd{display:grid;grid-template-columns:repeat(3,1fr);gap:5px 10px;margin-top:11px}
  .hdi{font-size:11px;color:var(--text3)}
  .hdv{font-family:'DM Mono',monospace;margin-top:1px;font-size:11px}
  #toast{position:fixed;bottom:max(28px,env(safe-area-inset-bottom,28px));left:50%;transform:translateX(-50%) translateY(20px);background:var(--text);color:var(--bg);padding:10px 22px;border-radius:24px;font-size:13px;font-weight:500;opacity:0;pointer-events:none;z-index:999;white-space:nowrap;transition:all 0.25s cubic-bezier(.4,0,.2,1);box-shadow:0 4px 20px rgba(0,0,0,0.5)}
  #toast.show{opacity:1;transform:translateX(-50%) translateY(0)}
  #saving{position:fixed;top:14px;right:14px;font-size:10px;color:var(--text3);font-family:'DM Mono',monospace;opacity:0;transition:opacity 0.3s;z-index:200}
  #saving.show{opacity:1}
  @media(max-width:430px){.sg{grid-template-columns:1fr 1fr}.sg .sc:last-child{grid-column:span 2}.cg{grid-template-columns:1fr}.bg2{grid-template-columns:1fr}.hd{grid-template-columns:1fr 1fr}h1{font-size:19px}.sv{font-size:15px}}
  @keyframes fadeUp{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
  .fade{animation:fadeUp 0.28s ease}
</style>
</head>
<body>
<header>
  <div class="hi">
    <div class="ht">
      <div><div class="lbl">Mein Budget</div><h1>Finanzübersicht 2026</h1></div>
      <div class="tabs">
        <button class="tab active" onclick="setView('month')">Monat</button>
        <button class="tab" onclick="setView('history')">Verlauf</button>
      </div>
    </div>
    <div class="mnav">
      <button class="nb" onclick="prevMonth()">‹</button>
      <div class="ml" id="monthLabel"></div>
      <button class="nb" onclick="nextMonth()">›</button>
    </div>
  </div>
</header>
<main>
  <div id="vm"></div>
  <div id="vh" style="display:none"></div>
</main>
<div id="toast"></div>
<div id="saving">💾 speichert…</div>
<script>
const CATS=[
  {id:"gastro",label:"Gastronomie & Bars",icon:"🍷",color:"#C8553D",def:300},
  {id:"shopping",label:"Shopping & Mode",icon:"🛍️",color:"#8B6F9B",def:150},
  {id:"reise",label:"Reise & Freizeit",icon:"✈️",color:"#4A7FA5",def:200},
  {id:"lebens",label:"Lebensmittel & Drogerie",icon:"🛒",color:"#5C8A5C",def:200},
  {id:"geschenke",label:"Geschenke",icon:"🎁",color:"#D4845A",def:80},
  {id:"bargeld",label:"Bargeld & Diverses",icon:"💶",color:"#8A7A5C",def:100},
];
const MONTHS=["Januar","Februar","März","April","Mai","Juni","Juli","August","September","Oktober","November","Dezember"];
const SALARY=3519,FIXED=1424,ETF=202,VARIABLE=SALARY-FIXED-ETF;
const SK="meinBudget2026_v2";
const SEED={"2026-0":{gastro:620,shopping:310,reise:888,lebens:80,geschenke:90,bargeld:250},"2026-1":{gastro:780,shopping:420,reise:650,lebens:85,geschenke:95,bargeld:250},"2026-2":{gastro:870,shopping:860,reise:545,lebens:90,geschenke:340,bargeld:200},"2026-3":{gastro:300,shopping:180,reise:431,lebens:70,geschenke:80,bargeld:100}};
let S={year:2026,month:new Date().getMonth(),view:"month",history:{},budgets:Object.fromEntries(CATS.map(c=>[c.id,c.def])),editCat:null,editMode:null};
function load(){try{const r=localStorage.getItem(SK);if(r){const d=JSON.parse(r);if(d.history)S.history=d.history;if(d.budgets)S.budgets=d.budgets;}}catch(e){}Object.entries(SEED).forEach(([k,v])=>{if(!S.history[k])S.history[k]=v;});}
let st=null;
function save(){const el=document.getElementById("saving");el.classList.add("show");clearTimeout(st);st=setTimeout(()=>{try{localStorage.setItem(SK,JSON.stringify({history:S.history,budgets:S.budgets}));}catch(e){}el.classList.remove("show");},600);}
const key=(y,m)=>`${y}-${m}`;
const ckey=()=>key(S.year,S.month);
const gs=id=>(S.history[ckey()]||{})[id]||0;
const fmt=n=>n.toLocaleString("de-DE",{maximumFractionDigits:0})+" €";
function ss(id,val){if(!S.history[ckey()])S.history[ckey()]={};S.history[ckey()][id]=Math.max(0,val);save();}
function ring(pct,color,sz=52){const r=sz/2-6,circ=2*Math.PI*r,dash=Math.min(pct/100,1)*circ,c=pct>100?"#E05252":color;return `<svg width="${sz}" height="${sz}" viewBox="0 0 ${sz} ${sz}" style="transform:rotate(-90deg);flex-shrink:0"><circle cx="${sz/2}" cy="${sz/2}" r="${r}" fill="none" stroke="rgba(255,255,255,0.08)" stroke-width="5"/><circle cx="${sz/2}" cy="${sz/2}" r="${r}" fill="none" stroke="${c}" stroke-width="5" stroke-linecap="round" stroke-dasharray="${dash} ${circ}" style="transition:stroke-dasharray 0.5s cubic-bezier(.4,0,.2,1)"/></svg>`;}
let tt=null;
function toast(msg){const el=document.getElementById("toast");el.textContent=msg;el.classList.add("show");clearTimeout(tt);tt=setTimeout(()=>el.classList.remove("show"),2200);}
function prevMonth(){if(S.month===0){S.month=11;S.year--;}else S.month--;S.editCat=null;render();}
function nextMonth(){if(S.month===11){S.month=0;S.year++;}else S.month++;S.editCat=null;render();}
function setView(v){S.view=v;S.editCat=null;render();}
function startEdit(id,mode){if(S.editCat===id&&S.editMode===mode){S.editCat=null;S.editMode=null;}else{S.editCat=id;S.editMode=mode;}render();if(S.editCat)setTimeout(()=>{const el=document.getElementById("inp-"+id);if(el)el.focus();},60);}
function confirmEdit(id){const el=document.getElementById("inp-"+id);if(!el)return;const val=parseFloat(el.value.replace(",","."));if(!isNaN(val)&&val>=0){if(S.editMode==="add"){ss(id,gs(id)+val);toast("+ "+fmt(val)+" eingetragen ✓");}else{ss(id,val);toast("Gespeichert ✓");}}S.editCat=null;S.editMode=null;render();}
function onKey(e,id){if(e.key==="Enter")confirmEdit(id);if(e.key==="Escape"){S.editCat=null;S.editMode=null;render();}}
function updateBudget(id,val){S.budgets[id]=Math.max(0,parseInt(val)||0);save();renderMonth();}
function render(){
  document.getElementById("monthLabel").textContent=MONTHS[S.month]+" "+S.year;
  document.querySelectorAll(".tab").forEach((t,i)=>t.classList.toggle("active",(i===0&&S.view==="month")||(i===1&&S.view==="history")));
  document.getElementById("vm").style.display=S.view==="month"?"":"none";
  document.getElementById("vh").style.display=S.view==="history"?"":"none";
  if(S.view==="month")renderMonth();else renderHistory();
}
function renderMonth(){
  const ts=CATS.reduce((a,c)=>a+gs(c.id),0),rem=VARIABLE-ts;
  let h=`<div class="sb"><div class="sd"></div><div><div style="font-size:12px;font-weight:500">iCloud Safari Sync aktiv</div><div style="font-size:11px;color:#4A7FA5;margin-top:1px">Daten synchronisieren sich automatisch zwischen deinen Apple-Geräten</div></div></div>
  <div class="sg">
    <div class="sc"><div class="sl">Gehalt netto</div><div class="sv" style="color:#5C8A5C">${fmt(SALARY)}</div><div class="ss">E.ON Foundation</div></div>
    <div class="sc"><div class="sl">Ausgegeben</div><div class="sv" style="color:${ts>VARIABLE?"#E05252":"#D4845A"}">${fmt(ts)}</div><div class="ss">von ${fmt(VARIABLE)}</div></div>
    <div class="sc"><div class="sl">${rem<0?"Überzogen":"Verbleibend"}</div><div class="sv" style="color:${rem<0?"#E05252":"#4A7FA5"}">${fmt(Math.abs(rem))}</div><div class="ss">${rem<0?"⚠ im Minus":"noch frei"}</div></div>
  </div>
  <div class="fb"><div><div class="lbl" style="margin-bottom:3px">Fixkosten (auto)</div><div style="font-size:11px;color:#777">Miete · BVG · Versicherungen · Telekom · Strom · Gewerkschaft · Abos · ETF</div></div><div style="font-size:17px;font-weight:600;white-space:nowrap">${fmt(FIXED+ETF)}</div></div>
  <div class="cg">`;
  CATS.forEach(cat=>{
    const s=gs(cat.id),b=S.budgets[cat.id],pct=b>0?(s/b)*100:0,over=s>b,active=S.editCat===cat.id;
    h+=`<div class="cc${over?" over":""}"><div class="ca" style="background:${cat.color}"></div>
      <div class="ct"><div><div class="ci">${cat.icon}</div><div class="cn">${cat.label}</div></div>${ring(pct,cat.color)}</div>`;
    if(active){h+=`<div class="ir"><input class="ii" id="inp-${cat.id}" type="number" min="0" step="0.01" placeholder="${S.editMode==="add"?"+ Betrag":s}" inputmode="decimal" onkeydown="onKey(event,'${cat.id}')"><button class="io" style="background:${cat.color}" onclick="confirmEdit('${cat.id}')">OK</button></div>`;}
    else{h+=`<div class="cam"><span class="cs" style="color:${over?"#E05252":"#F0EDE8"}">${s.toLocaleString("de-DE",{maximumFractionDigits:0})}</span><span class="co">/ ${b} €</span></div>`;}
    h+=`<div class="pb"><div class="pf" style="width:${Math.min(pct,100)}%;background:${over?"#E05252":cat.color}"></div></div>
      <div class="cac"><button class="cb" onclick="startEdit('${cat.id}','add')">+ Ausgabe</button><button class="cb" onclick="startEdit('${cat.id}','set')">Gesamt setzen</button></div></div>`;
  });
  h+=`</div><div class="be" style="margin-top:13px"><div class="lbl" style="margin-bottom:12px">Budget anpassen</div><div class="bg2">`;
  CATS.forEach(cat=>{h+=`<div class="br"><span style="font-size:13px">${cat.icon}</span><span style="font-size:12px;color:#777;flex:1;min-width:0;overflow:hidden;text-overflow:ellipsis;white-space:nowrap">${cat.label.split(" ")[0]}</span><input class="bi" type="number" min="0" value="${S.budgets[cat.id]}" inputmode="numeric" onchange="updateBudget('${cat.id}',this.value)"><span style="font-size:11px;color:#444">€</span></div>`;});
  h+=`</div></div>`;
  document.getElementById("vm").innerHTML=h;
}
function renderHistory(){
  const keys=Object.keys(S.history).sort().slice(-8).reverse();
  const tb=Object.values(S.budgets).reduce((a,b)=>a+b,0);
  let h=`<p style="font-size:13px;color:#555;margin:0 0 14px">Letzte ${keys.length} Monate · gespeichert via iCloud ☁️</p>`;
  keys.forEach(k=>{
    const[y,m]=k.split("-"),data=S.history[k]||{};
    const total=CATS.reduce((a,c)=>a+(data[c.id]||0),0),over=total>tb,isSeed=Object.keys(SEED).includes(k);
    const cm=Math.max(...CATS.map(c=>data[c.id]||0),1);
    h+=`<div class="hc${over?" over":""}"><div class="hh"><div style="display:flex;align-items:center;gap:8px"><span style="font-size:14px;font-weight:500">${MONTHS[parseInt(m)]} ${y}</span>${isSeed?`<span style="font-size:9px;color:#444;font-family:'DM Mono',monospace">aus Kontoauszug</span>`:""}</div><span style="font-size:16px;font-weight:600;color:${over?"#E05252":"#5C8A5C"};font-family:'DM Mono',monospace">${fmt(total)}</span></div>
    <div class="hbars">`;
    CATS.forEach(cat=>{const v=data[cat.id]||0,hh=Math.max((v/cm)*34,v>0?3:0);h+=`<div class="hbar" style="height:${hh}px;background:${cat.color}" title="${cat.label}: ${fmt(v)}"></div>`;});
    h+=`</div><div class="hicons">`;
    CATS.forEach(cat=>{h+=`<div class="hic">${cat.icon}</div>`;});
    h+=`</div><div class="hd">`;
    CATS.forEach(cat=>{const v=data[cat.id]||0,b=S.budgets[cat.id];h+=`<div class="hdi">${cat.icon} ${cat.label.split(" ")[0]}<div class="hdv" style="color:${v>b?"#E05252":"#888"}">${fmt(v)}</div></div>`;});
    h+=`</div></div>`;
  });
  h+=`<div style="background:rgba(255,255,255,0.02);border-radius:10px;padding:11px 14px;margin-top:4px"><p style="font-size:11px;color:#3a3a3a;text-align:center;font-family:'DM Mono',monospace;margin:0">Jan–Apr aus deinen Kontoauszügen · danach selbst eintragen</p></div>`;
  document.getElementById("vh").innerHTML=h;
}
load();render();
</script>
</body>
</html>
