<!doctype html>
<html lang="ja">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>江ノ島電鉄 駅図</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.css">
<style>
@import url('https://fonts.googleapis.com/css2?family=Shippori+Mincho:wght@500;700&family=Zen+Kaku+Gothic+New:wght@400;500;700;900&display=swap');

:root{
  --bg:#f3f0e8; --paper:#fbf9f4; --ink:#1d2420; --ink-dim:#5b6560;
  --line-hair:#d8d2c3; --accent:#0e7a6b; --accent-ink:#fff;
  --sheet-shadow:0 -12px 40px rgba(29,36,32,.18);
  --rail:#0e7a6b; --dot-stroke:#fbf9f4; --chip-bg:#eee9dc; --chip-ink:#5b6560;
  --now-bg:#0e7a6b; --now-ink:#fff; --pos-bg:#c14a36; --warn-bg:#f4e3c1; --warn-ink:#6b4d1a;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#11151a; --paper:#171c22; --ink:#eae6da; --ink-dim:#8b948d;
    --line-hair:#2a3138; --accent:#4fd0bb; --accent-ink:#0c1512;
    --sheet-shadow:0 -12px 40px rgba(0,0,0,.5);
    --rail:#4fd0bb; --dot-stroke:#171c22; --chip-bg:#232a31; --chip-ink:#8b948d;
    --now-bg:#4fd0bb; --now-ink:#0c1512; --pos-bg:#e07a5f; --warn-bg:#3a301a; --warn-ink:#e0c98a;
  }
}
:root[data-theme="dark"]{
  --bg:#11151a; --paper:#171c22; --ink:#eae6da; --ink-dim:#8b948d;
  --line-hair:#2a3138; --accent:#4fd0bb; --accent-ink:#0c1512;
  --sheet-shadow:0 -12px 40px rgba(0,0,0,.5);
  --rail:#4fd0bb; --dot-stroke:#171c22; --chip-bg:#232a31; --chip-ink:#8b948d;
  --now-bg:#4fd0bb; --now-ink:#0c1512; --pos-bg:#e07a5f; --warn-bg:#3a301a; --warn-ink:#e0c98a;
}

*{box-sizing:border-box;}
html,body{height:100%;margin:0;}
body{
  background:var(--bg); color:var(--ink);
  font-family:'Zen Kaku Gothic New','Hiragino Sans',sans-serif;
  overscroll-behavior:none; -webkit-tap-highlight-color:transparent;
}
.app{height:100%;display:flex;flex-direction:column;max-width:560px;margin:0 auto;position:relative;}

header{
  flex:0 0 auto; padding:calc(14px + env(safe-area-inset-top,0px)) 18px 10px;
  display:flex;align-items:baseline;justify-content:space-between;gap:12px;
  border-bottom:1px solid var(--line-hair); background:var(--paper); z-index:5;
}
header h1{font-family:'Shippori Mincho',serif;font-weight:700;font-size:1.4rem;margin:0;letter-spacing:.04em;}
header .sub{font-size:.66rem;color:var(--ink-dim);letter-spacing:.08em;}
.clock{font-variant-numeric:tabular-nums;font-size:.85rem;color:var(--ink-dim);text-align:right;line-height:1.3;}
.clock b{color:var(--ink);font-weight:700;font-size:1rem;}

.status-strip{
  flex:0 0 auto; padding:7px 18px; font-size:.7rem; color:var(--ink-dim);
  background:var(--paper); border-bottom:1px solid var(--line-hair); display:flex; gap:8px; align-items:center;
}
.status-strip .dot{width:7px;height:7px;border-radius:50%;background:var(--rail);flex:0 0 auto;}
.status-strip.warn{background:var(--warn-bg);color:var(--warn-ink);}
.status-strip.warn .dot{background:var(--warn-ink);}

#map{flex:1 1 auto;background:var(--bg);}
.leaflet-container{font-family:inherit;background:var(--bg) !important;}

.st-marker{
  width:16px;height:16px;border-radius:50%;background:var(--rail);
  border:3px solid var(--dot-stroke);box-shadow:0 1px 4px rgba(0,0,0,.4);
}
.st-marker.active{background:var(--pos-bg);width:20px;height:20px;}
.st-label{
  font-family:'Zen Kaku Gothic New',sans-serif; font-weight:700; font-size:12px;
  color:var(--ink); background:var(--paper); padding:1px 6px; border-radius:5px;
  border:1px solid var(--line-hair); white-space:nowrap; box-shadow:0 1px 3px rgba(0,0,0,.15);
}

.hint{
  position:absolute;left:50%;bottom:calc(14px + env(safe-area-inset-bottom,0px));
  transform:translateX(-50%); background:var(--chip-bg); color:var(--chip-ink);
  font-size:.72rem;padding:7px 14px;border-radius:999px;pointer-events:none;
  transition:opacity .3s; white-space:nowrap; text-align:center; z-index:400;
}
.hint.hidden{opacity:0;}

.sheet-backdrop{position:fixed;inset:0;background:rgba(10,12,10,.32);opacity:0;pointer-events:none;transition:opacity .22s ease;z-index:1000;}
.sheet-backdrop.open{opacity:1;pointer-events:auto;}
.sheet{
  position:fixed;left:50%;bottom:0;transform:translate(-50%,100%);width:100%;max-width:560px;
  max-height:82%;background:var(--paper);border-radius:20px 20px 0 0;box-shadow:var(--sheet-shadow);
  transition:transform .28s cubic-bezier(.32,.72,0,1);z-index:1001;display:flex;flex-direction:column;
  padding-bottom:env(safe-area-inset-bottom,0px);
}
.sheet.open{transform:translate(-50%,0);}
.sheet-grip{width:36px;height:4px;border-radius:2px;background:var(--line-hair);margin:10px auto 4px;flex:0 0 auto;}
.sheet-head{padding:6px 20px 12px;border-bottom:1px solid var(--line-hair);flex:0 0 auto;position:relative;}
.sheet-head h2{margin:0;font-family:'Shippori Mincho',serif;font-size:1.3rem;font-weight:700;}
.sheet-head .romaji{font-size:.72rem;color:var(--ink-dim);letter-spacing:.05em;}
.close-btn{
  position:absolute;right:14px;top:14px;width:30px;height:30px;border-radius:50%;border:none;
  background:var(--chip-bg);color:var(--chip-ink);font-size:16px;display:flex;align-items:center;
  justify-content:center;cursor:pointer;
}
.back-btn{
  border:none;background:var(--chip-bg);color:var(--ink);font-family:inherit;font-size:.78rem;
  font-weight:700;padding:6px 12px 6px 10px;border-radius:999px;display:inline-flex;align-items:center;
  gap:4px;cursor:pointer;margin-bottom:8px;
}
.tabs{display:flex;flex:0 0 auto;border-bottom:1px solid var(--line-hair);}
.tab{flex:1;text-align:center;padding:11px 4px;font-size:.82rem;color:var(--ink-dim);font-weight:700;
  cursor:pointer;border-bottom:2px solid transparent;background:none;border:none;font-family:inherit;}
.tab.active{color:var(--accent);border-bottom-color:var(--accent);}
.panel{overflow-y:auto;padding:4px 0 18px;}
.tt-row{
  display:grid;grid-template-columns:52px 1fr auto;align-items:center;gap:10px;
  padding:10px 20px;border-bottom:1px solid var(--line-hair);font-variant-numeric:tabular-nums;
  cursor:pointer; background:none; border-left:none;border-right:none;border-top:none; width:100%;
  text-align:left; font-family:inherit; color:inherit;
}
.tt-row.next{background:linear-gradient(90deg, color-mix(in srgb, var(--accent) 12%, transparent), transparent);}
.tt-time{font-size:1.05rem;font-weight:700;}
.tt-dest{font-size:.86rem;color:var(--ink);}
.tt-dest .via{display:block;font-size:.7rem;color:var(--ink-dim);font-weight:400;margin-top:1px;}
.chev{color:var(--ink-dim);font-size:.9rem;}
.now-chip{
  background:var(--now-bg);color:var(--now-ink);font-size:.68rem;font-weight:700;
  padding:3px 9px;border-radius:999px;display:inline-flex;align-items:center;gap:5px;margin:10px 20px 2px;
}
.now-chip .pulse{width:6px;height:6px;border-radius:50%;background:currentColor;animation:pulse 1.6s ease-in-out infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:.3;}}
@media (prefers-reduced-motion:reduce){.now-chip .pulse{animation:none;}}
.trip-head{padding:2px 20px 10px;}
.trip-head .route{font-size:.78rem;color:var(--ink-dim);}
.trip-badge{
  display:inline-block;font-size:.68rem;font-weight:700;background:var(--chip-bg);color:var(--chip-ink);
  padding:2px 8px;border-radius:5px;margin-right:6px;
}
.stop-row{display:grid;grid-template-columns:70px 22px 1fr;align-items:start;gap:10px;padding:8px 20px;position:relative;}
.stop-row .times{font-variant-numeric:tabular-nums;font-size:.78rem;color:var(--ink-dim);text-align:right;line-height:1.5;}
.stop-row .times b{display:block;font-size:.95rem;color:var(--ink);font-weight:700;}
.stop-line{display:flex;flex-direction:column;align-items:center;height:100%;}
.stop-line .seg{flex:1;width:2px;background:var(--line-hair);}
.stop-line .node{width:11px;height:11px;border-radius:50%;background:var(--rail);border:2px solid var(--paper);box-shadow:0 0 0 1px var(--line-hair);flex:0 0 auto;}
.stop-row.origin .stop-line .node,.stop-row.dest .stop-line .node{background:var(--pos-bg);width:13px;height:13px;}
.stop-row .name{font-size:.92rem;padding-top:1px;}
.stop-row.origin .name,.stop-row.dest .name{font-weight:700;}
.stop-row .tag{font-size:.65rem;color:var(--accent-ink);background:var(--pos-bg);padding:1px 6px;border-radius:4px;margin-left:6px;}
.note{background:var(--chip-bg);border-radius:10px;padding:10px 14px;margin:10px 20px 0;font-size:.72rem;color:var(--ink-dim);line-height:1.6;}
</style>
</head>
<body>
<div class="app">
  <header>
    <div>
      <h1>江ノ島電鉄線</h1>
      <div class="sub">実地図版（OpenStreetMap）</div>
    </div>
    <div class="clock"><b id="clockTime">--:--</b><br><span id="clockDate">----.--.--</span></div>
  </header>
  <div class="status-strip" id="statusStrip"><span class="dot"></span><span id="statusText">駅座標を読み込み中…</span></div>

  <div id="map"></div>
  <div class="hint" id="hint">駅をタップすると発車時刻、時刻をタップすると各駅の到着・発車時刻が見られます</div>
</div>

<div class="sheet-backdrop" id="backdrop"></div>
<div class="sheet" id="sheet" role="dialog" aria-modal="true">
  <div class="sheet-grip"></div>
  <button class="close-btn" id="closeBtn" aria-label="閉じる">✕</button>
  <div id="viewStation">
    <div class="sheet-head">
      <h2 id="sheetName">-</h2>
      <div class="romaji" id="sheetRomaji">-</div>
    </div>
    <div class="tabs">
      <button class="tab active" data-dir="down">鎌倉方面</button>
      <button class="tab" data-dir="up">藤沢方面</button>
    </div>
    <div class="panel" id="timetableBody"></div>
  </div>
  <div id="viewTrip" style="display:none;flex:1;min-height:0;display:flex;flex-direction:column;">
    <div class="trip-head">
      <button class="back-btn" id="backBtn">← 発車時刻に戻る</button>
      <div class="route" id="tripRoute">-</div>
    </div>
    <div class="panel" id="tripBody" style="flex:1;"></div>
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.js"></script>
<script>
(function(){
"use strict";

/* ================= Real timetable data (verified, scraped) =================
   Source: ekitan.com station timetable pages for 江ノ島電鉄線.
   Fujisawa-departure (down, Kamakura-bound) and Kamakura-departure
   (up, Fujisawa-bound) lists below were fetched directly from those pages
   and are the SATURDAY (土曜) timetable — the page defaulted to Saturday at
   fetch time (2026-09-12 reference date), not the weekday timetable. That is
   disclosed in the UI. Intermediate-station times are NOT individually
   scraped; they are derived by distributing each trip's real terminal-to-
   terminal time across the real OSM-measured distances between stations,
   using Enoden's commonly published ~34 minute end-to-end running time. So:
   terminal departure minutes = real, verified. Intermediate arrival/departure
   minutes = geometrically-proportioned estimates, not individually verified. */

const FUJISAWA_DOWN = { // 藤沢発 → 鎌倉方面, 土曜ダイヤ
  5:[36,50], 6:[4,18,32,46], 7:[0,14,28,42,56], 8:[10,24,38,52], 9:[6,20,34,48],
  10:[2,16,30,44,58], 11:[12,26,40,54], 12:[8,22,36,50], 13:[4,18,32,46],
  14:[0,14,28,42,56], 15:[10,24,38,52], 16:[6,20,34,48], 17:[2,16,30,44,58],
  18:[12,26,40,54], 19:[8,22,36,50], 20:[4,18,32,46], 21:[0,14,28,42,56],
  22:[10,24,50], 23:[16,42]
};
const KAMAKURA_UP = { // 鎌倉発 → 藤沢方面, 土曜ダイヤ
  5:[20,34,50], 6:[4,18,32,46], 7:[0,14,28,42,56], 8:[10,24,38,52], 9:[6,20,34,48],
  10:[2,16,30,44,58], 11:[12,26,40,54], 12:[8,22,36,50], 13:[4,18,32,46],
  14:[0,14,28,42,56], 15:[10,24,38,52], 16:[6,20,34,48], 17:[2,16,30,44,58],
  18:[12,26,40,54], 19:[8,22,36,50], 20:[4,18,32,46], 21:[0,14,28,42],
  22:[10,24,39], 23:[5,38]
};
function tableToSeconds(table){
  const out=[];
  Object.keys(table).forEach(h=>{ table[h].forEach(m=> out.push(parseInt(h)*3600+m*60)); });
  return out.sort((a,b)=>a-b);
}
const DOWN_STARTS = tableToSeconds(FUJISAWA_DOWN);
const UP_STARTS = tableToSeconds(KAMAKURA_UP);

/* ================= Station list (real order) + fallback coordinates =================
   Fallback coordinates are approximate (used only if the live OSM lookup
   below fails, e.g. no network). When the live lookup succeeds, these are
   overwritten with real OpenStreetMap node coordinates. */
const STATION_DEFS = [
  {id:"fujisawa", name:"藤沢", romaji:"Fujisawa", osm:"藤沢駅", fallback:[35.3389,139.4909], poi:"小田急・JR接続"},
  {id:"ishigami", name:"石上", romaji:"Ishigami", osm:"石上駅", fallback:[35.3323,139.4875]},
  {id:"yanagikoji", name:"柳小路", romaji:"Yanagikoji", osm:"柳小路駅", fallback:[35.3277,139.4844]},
  {id:"kugenuma", name:"鵠沼", romaji:"Kugenuma", osm:"鵠沼駅", fallback:[35.3223,139.4805]},
  {id:"shonan", name:"湘南海岸公園", romaji:"Shonan-kaigan-kōen", osm:"湘南海岸公園駅", fallback:[35.3128,139.4787]},
  {id:"enoshima", name:"江ノ島", romaji:"Enoshima", osm:"江ノ島駅", fallback:[35.3079,139.4805], poi:"小田急江ノ島線接続"},
  {id:"koshigoe", name:"腰越", romaji:"Koshigoe", osm:"腰越駅", fallback:[35.3059,139.4870]},
  {id:"kamakurakokomae", name:"鎌倉高校前", romaji:"Kamakurakōkōmae", osm:"鎌倉高校前駅", fallback:[35.3049,139.5011], poi:"海側ビュースポット"},
  {id:"shichirigahama", name:"七里ヶ浜", romaji:"Shichirigahama", osm:"七里ヶ浜駅", fallback:[35.3068,139.5111]},
  {id:"inamuragasaki", name:"稲村ヶ崎", romaji:"Inamuragasaki", osm:"稲村ヶ崎駅", fallback:[35.3092,139.5228]},
  {id:"gokurakuji", name:"極楽寺", romaji:"Gokurakuji", osm:"極楽寺駅", fallback:[35.3117,139.5325]},
  {id:"hase", name:"長谷", romaji:"Hase", osm:"長谷駅 (神奈川県)", fallback:[35.3145,139.5411], poi:"長谷寺・大仏"},
  {id:"yuigahama", name:"由比ヶ浜", romaji:"Yuigahama", osm:"由比ヶ浜駅", fallback:[35.3151,139.5473]},
  {id:"wadazuka", name:"和田塚", romaji:"Wadazuka", osm:"和田塚駅", fallback:[35.3168,139.5513]},
  {id:"kamakura", name:"鎌倉", romaji:"Kamakura", osm:"鎌倉駅", fallback:[35.3189,139.5525], poi:"JR横須賀線接続"}
];

function haversine(lat1,lon1,lat2,lon2){
  const R=6371000, p1=lat1*Math.PI/180, p2=lat2*Math.PI/180;
  const dp=(lat2-lat1)*Math.PI/180, dl=(lon2-lon1)*Math.PI/180;
  const a=Math.sin(dp/2)**2+Math.cos(p1)*Math.cos(p2)*Math.sin(dl/2)**2;
  return 2*R*Math.asin(Math.sqrt(a));
}

let STATIONS = STATION_DEFS.map(s=>({...s, lat:s.fallback[0], lon:s.fallback[1], live:false}));
let map, railLine, markers = {};
let usingLive = false;

function computeDistances(){
  let cum=0;
  STATIONS.forEach((s,i)=>{
    if(i>0) cum += haversine(STATIONS[i-1].lat, STATIONS[i-1].lon, s.lat, s.lon);
    s.cumM = cum;
  });
}
computeDistances();

/* ================= Map init (real OSM tiles) ================= */
function initMap(){
  map = L.map('map', {zoomControl:true, attributionControl:true});
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
  }).addTo(map);
  drawStations();
  const bounds = L.latLngBounds(STATIONS.map(s=>[s.lat,s.lon]));
  map.fitBounds(bounds, {padding:[40,40]});
}

function drawStations(){
  if(railLine) map.removeLayer(railLine);
  Object.values(markers).forEach(m=>map.removeLayer(m));
  markers = {};

  railLine = L.polyline(STATIONS.map(s=>[s.lat,s.lon]), {
    color: getComputedStyle(document.documentElement).getPropertyValue('--rail').trim() || '#0e7a6b',
    weight: 5, opacity: 0.9, lineJoin:'round'
  }).addTo(map);

  STATIONS.forEach(s=>{
    const icon = L.divIcon({className:'', html:`<div class="st-marker" id="mk-${s.id}"></div>`, iconSize:[16,16], iconAnchor:[8,8]});
    const marker = L.marker([s.lat,s.lon], {icon}).addTo(map);
    const label = L.tooltip({permanent:true, direction:'right', offset:[10,0], className:'st-label-wrap', opacity:1})
      .setContent(`<span class="st-label">${s.name}</span>`);
    marker.bindTooltip(label);
    marker.on('click', ()=> openStation(s, marker));
    markers[s.id] = marker;
  });
}

/* ================= Live OSM lookup (runs in the user's own browser — no
   sandbox restriction here, unlike a hosted Artifact page). Falls back to
   the approximate coordinates above if it fails (offline, blocked, etc). */
async function loadLiveStationData(){
  const statusEl = document.getElementById("statusText");
  const stripEl = document.getElementById("statusStrip");
  try{
    const query = `[out:json][timeout:25];
      area["name"="神奈川県"]->.pref;
      (
        node["railway"="station"]["name"~"藤沢|石上|柳小路|鵠沼|湘南海岸公園|江ノ島|腰越|鎌倉高校前|七里ヶ浜|稲村ヶ崎|極楽寺|長谷|由比ヶ浜|和田塚|鎌倉"](area.pref);
      );
      out body;`;
    const res = await fetch('https://overpass-api.de/api/interpreter', {
      method:'POST', body:'data='+encodeURIComponent(query)
    });
    if(!res.ok) throw new Error('overpass http '+res.status);
    const data = await res.json();
    let matched = 0;
    STATIONS.forEach(s=>{
      const hit = data.elements.find(el => el.tags && el.tags.name === s.name + "駅");
      if(hit){ s.lat = hit.lat; s.lon = hit.lon; s.live = true; matched++; }
    });
    computeDistances();
    if(matched >= 8){
      usingLive = true;
      stripEl.classList.remove('warn');
      statusEl.textContent = `OpenStreetMapの実座標を使用中（${matched}/${STATIONS.length}駅を照合）`;
    } else {
      stripEl.classList.add('warn');
      statusEl.textContent = `実座標の照合が一部のみ（${matched}/${STATIONS.length}駅）。残りは概算座標で補完`;
    }
  }catch(err){
    stripEl.classList.add('warn');
    statusEl.textContent = "オフラインのため概算座標で表示中（電波の届く場所で再読み込みすると実座標に切替）";
  }
  drawStations();
}

/* ================= Trip generation from REAL terminal times ================= */
const TOTAL_M = () => STATIONS[STATIONS.length-1].cumM;
const RUN_SEC = 34*60 - (STATIONS.length-2)*15; // ~34min published end-to-end minus est. dwell

function buildTrip(startSec, dir){
  const seq = dir === "down" ? STATIONS : STATIONS.slice().reverse();
  const total = TOTAL_M();
  const secPerM = total > 0 ? RUN_SEC/total : 0;
  let t = startSec;
  const stops = seq.map((s,i)=>{
    if(i>0){
      const prev = seq[i-1];
      const segM = Math.abs(s.cumM - prev.cumM);
      t += segM * secPerM;
    }
    const arr = t;
    const dwell = (i===0 || i===seq.length-1) ? 0 : 15;
    t += dwell;
    return {station:s, arr, dep:t};
  });
  return {dir, dest: seq[seq.length-1], origin: seq[0], stops};
}
function fmt(sec){
  sec = Math.round(sec/5)*5;
  const h = Math.floor(sec/3600)%24, m = Math.floor((sec%3600)/60);
  return {label:`${String(h).padStart(2,"0")}:${String(m).padStart(2,"0")}`};
}
function getTrips(){
  return {
    down: DOWN_STARTS.map(s=>buildTrip(s,"down")),
    up: UP_STARTS.map(s=>buildTrip(s,"up"))
  };
}
function tripsFromStation(stationId, dir){
  const trips = getTrips()[dir];
  return trips.map(trip=>({trip, stop:trip.stops.find(st=>st.station.id===stationId)}))
    .filter(x=>x.stop).sort((a,b)=>a.stop.dep-b.stop.dep);
}

/* ================= Sheet UI ================= */
const backdrop = document.getElementById("backdrop");
const sheet = document.getElementById("sheet");
const sheetName = document.getElementById("sheetName");
const sheetRomaji = document.getElementById("sheetRomaji");
const timetableBody = document.getElementById("timetableBody");
const viewStation = document.getElementById("viewStation");
const viewTrip = document.getElementById("viewTrip");
const tripBody = document.getElementById("tripBody");
const tripRoute = document.getElementById("tripRoute");
const hint = document.getElementById("hint");
const tabs = document.querySelectorAll(".tab");

let activeMarkerId = null;
let currentStation = null;
let currentDir = "down";

function nowSec(){ const d=new Date(); return d.getHours()*3600+d.getMinutes()*60+d.getSeconds(); }

function renderStationTimetable(station, dir){
  const list = tripsFromStation(station.id, dir);
  const now = nowSec();
  let nextMarked = false;
  const rowsHtml = list.map(({trip, stop})=>{
    const t = fmt(stop.dep);
    const isNext = !nextMarked && stop.dep >= now;
    if(isNext) nextMarked = true;
    return `<button class="tt-row ${isNext?'next':''}" data-trip-start="${trip.stops[0].dep}" data-dir="${dir}">
      <span class="tt-time">${t.label}</span>
      <span class="tt-dest">${trip.dest.name}ゆき<span class="via">普通・全駅停車</span></span>
      <span class="chev">›</span>
    </button>`;
  }).join("");
  const next = list.find(({stop})=>stop.dep>=now);
  const nowChip = next
    ? `<div class="now-chip"><span class="pulse"></span>次発 ${fmt(next.stop.dep).label} ${next.trip.dest.name}ゆき</div>`
    : `<div class="now-chip"><span class="pulse"></span>本日の掲載時刻表の運行は終了しました</div>`;
  timetableBody.innerHTML = nowChip + rowsHtml +
    `<div class="note">起点(藤沢)・終点(鎌倉)の発車時刻は ekitan.com の土曜ダイヤを実データとして使用。途中駅の時刻は実測距離に基づく按分の推定値です。実際の平日ダイヤは公式サイトでご確認ください。</div>`;
  requestAnimationFrame(()=>{
    const nextEl = timetableBody.querySelector(".tt-row.next");
    if(nextEl) nextEl.scrollIntoView({block:"center"});
  });
  timetableBody.querySelectorAll(".tt-row").forEach(row=>{
    row.addEventListener("click", ()=>{
      const start = Number(row.dataset.tripStart);
      const rdir = row.dataset.dir;
      const trip = getTrips()[rdir].find(tr=>Math.round(tr.stops[0].dep)===Math.round(start));
      if(trip) openTrip(trip, station.id);
    });
  });
}

function openTrip(trip, focusStationId){
  viewStation.style.display = "none";
  viewTrip.style.display = "flex";
  tripRoute.innerHTML = `<span class="trip-badge">普通</span>${trip.origin.name} → ${trip.dest.name}　全駅停車`;
  const now = nowSec();
  const rows = trip.stops.map((st,i)=>{
    const isOrigin = i===0, isDest = i===trip.stops.length-1;
    const isFocus = st.station.id === focusStationId;
    const passed = st.dep < now;
    const timesHtml = isOrigin ? `<b>${fmt(st.dep).label}</b>発`
      : isDest ? `<b>${fmt(st.arr).label}</b>着`
      : `${fmt(st.arr).label}着<b>${fmt(st.dep).label}</b>発`;
    return `<div class="stop-row ${isOrigin?'origin':''} ${isDest?'dest':''}" style="opacity:${passed?0.45:1}">
      <div class="times">${timesHtml}</div>
      <div class="stop-line">
        <div class="seg" style="${i===0?'background:transparent':''}"></div>
        <div class="node"></div>
        <div class="seg" style="${i===trip.stops.length-1?'background:transparent':''}"></div>
      </div>
      <div class="name">${st.station.name}${isFocus?'<span class="tag">選択駅</span>':''}${st.station.poi?`<br><span style="font-size:.7rem;color:var(--ink-dim);font-weight:400;">${st.station.poi}</span>`:''}</div>
    </div>`;
  }).join("");
  tripBody.innerHTML = rows + `<div class="note">起終点の発車時刻は実データ、途中駅は距離按分の推定値です（公式ダイヤと厳密には一致しません）。</div>`;
  requestAnimationFrame(()=>{
    const idx = trip.stops.findIndex(s=>s.station.id===focusStationId);
    const focusEl = [...tripBody.querySelectorAll(".stop-row")][idx];
    if(focusEl) focusEl.scrollIntoView({block:"center"});
  });
}

function backToStation(){ viewTrip.style.display="none"; viewStation.style.display="block"; }

function openStation(station, marker){
  if(activeMarkerId){
    const prevEl = document.getElementById('mk-'+activeMarkerId);
    if(prevEl) prevEl.classList.remove('active');
  }
  activeMarkerId = station.id;
  const el = document.getElementById('mk-'+station.id);
  if(el) el.classList.add('active');

  currentStation = station;
  currentDir = "down";
  tabs.forEach(t=>t.classList.toggle("active", t.dataset.dir==="down"));
  sheetName.textContent = station.name + "駅";
  sheetRomaji.textContent = station.romaji + (station.poi?" ・ "+station.poi:"") + (station.live?" ・ 実座標":" ・ 概算座標");
  backToStation();
  renderStationTimetable(station, "down");
  backdrop.classList.add("open");
  sheet.classList.add("open");
  hint.classList.add("hidden");
  map.panTo([station.lat, station.lon]);
}

function closeSheet(){
  backdrop.classList.remove("open");
  sheet.classList.remove("open");
  if(activeMarkerId){
    const el = document.getElementById('mk-'+activeMarkerId);
    if(el) el.classList.remove('active');
    activeMarkerId = null;
  }
}

backdrop.addEventListener("click", closeSheet);
document.getElementById("closeBtn").addEventListener("click", closeSheet);
document.getElementById("backBtn").addEventListener("click", backToStation);
tabs.forEach(t=>t.addEventListener("click", ()=>{
  tabs.forEach(x=>x.classList.remove("active"));
  t.classList.add("active");
  currentDir = t.dataset.dir;
  backToStation();
  if(currentStation) renderStationTimetable(currentStation, currentDir);
}));
document.addEventListener("keydown", (e)=>{ if(e.key==="Escape") closeSheet(); });

function tickClock(){
  const d = new Date();
  document.getElementById("clockTime").textContent = `${String(d.getHours()).padStart(2,"0")}:${String(d.getMinutes()).padStart(2,"0")}`;
  document.getElementById("clockDate").textContent = `${d.getFullYear()}.${String(d.getMonth()+1).padStart(2,"0")}.${String(d.getDate()).padStart(2,"0")}`;
}
tickClock();
setInterval(tickClock, 15000);

document.getElementById("map").addEventListener("touchstart", ()=>{ hint.classList.add("hidden"); }, {once:true, passive:true});
document.getElementById("map").addEventListener("mousedown", ()=>{ hint.classList.add("hidden"); }, {once:true});

initMap();
loadLiveStationData();

})();
</script>
</body>
</html>
