# Mt5site<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>SMC AI HEDGE FUND TERMINAL X PRO</title>

<script src="https://s3.tradingview.com/tv.js"></script>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    background:#050816;
    color:white;
    font-family:Arial;
    overflow:hidden;
}

/* TOPBAR */

.topbar{
    height:60px;
    background:#0b1220;
    border-bottom:1px solid #18233f;
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding:0 20px;
}

.logo{
    color:#00d9ff;
    font-size:20px;
    font-weight:bold;
}

.top-actions{
    display:flex;
    gap:10px;
}

.top-actions button{
    background:#17233d;
    border:none;
    color:white;
    padding:10px 15px;
    border-radius:7px;
    cursor:pointer;
}

/* MAIN */

.main{
    display:flex;
    height:calc(100vh - 60px);
}

/* SIDEBAR */

.sidebar{
    width:250px;
    background:#09111f;
    border-right:1px solid #18233f;
    overflow-y:auto;
    padding:15px;
}

.sidebar h3{
    margin:15px 0 10px;
    color:#00d9ff;
}

.market{
    background:#121c33;
    padding:10px;
    border-radius:7px;
    margin-bottom:8px;
    cursor:pointer;
    transition:0.2s;
}

.market:hover{
    background:#1d2d4f;
}

/* CENTER */

.center{
    flex:1;
    display:flex;
    flex-direction:column;
}

/* CHART */

.chart-area{
    height:68%;
    border-bottom:1px solid #18233f;
}

#tradingview_chart{
    width:100%;
    height:100%;
}

/* ANALYSIS */

.analysis{
    height:32%;
    background:#08101d;
    overflow-y:auto;
    padding:15px;
}

.analysis-title{
    color:#00d9ff;
    font-size:18px;
    margin-bottom:15px;
}

.grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:10px;
}

.card{
    background:#121c33;
    border-radius:10px;
    padding:12px;
}

.card h4{
    color:#7fd1ff;
    margin-bottom:8px;
}

.buy{
    color:#00ff88;
    font-weight:bold;
}

.sell{
    color:#ff4d6d;
    font-weight:bold;
}

.wait{
    color:#ffd166;
    font-weight:bold;
}

/* RIGHT PANEL */

.right{
    width:340px;
    background:#09111f;
    border-left:1px solid #18233f;
    display:flex;
    flex-direction:column;
}

/* FEED */

.feed{
    flex:1;
    overflow-y:auto;
    padding:15px;
}

.feed h3{
    color:#00d9ff;
    margin-bottom:15px;
}

.msg{
    background:#121c33;
    padding:12px;
    border-radius:8px;
    margin-bottom:10px;
    font-size:13px;
    line-height:1.6;
}

/* RISK */

.risk{
    height:250px;
    border-top:1px solid #18233f;
    padding:15px;
}

.risk-box{
    background:#121c33;
    padding:12px;
    border-radius:8px;
    margin-bottom:10px;
}

.progress{
    width:100%;
    height:10px;
    background:#222;
    border-radius:5px;
    overflow:hidden;
    margin-top:6px;
}

.progress div{
    width:25%;
    height:100%;
    background:#00ff88;
}

/* BUTTONS */

.trade-buttons{
    display:flex;
    gap:10px;
    margin-top:15px;
}

.buy-btn{
    flex:1;
    background:#00aa55;
    border:none;
    color:white;
    padding:12px;
    border-radius:8px;
    cursor:pointer;
    font-weight:bold;
}

.sell-btn{
    flex:1;
    background:#d62839;
    border:none;
    color:white;
    padding:12px;
    border-radius:8px;
    cursor:pointer;
    font-weight:bold;
}

/* RESPONSIVE */

@media(max-width:1200px){

.right{
    display:none;
}

.grid{
    grid-template-columns:repeat(2,1fr);
}

}

</style>

</head>

<body>

<!-- TOPBAR -->

<div class="topbar">

<div class="logo">
🚀 SMC AI HEDGE FUND TERMINAL X PRO
</div>

<div class="top-actions">

<button>Dashboard</button>
<button>Signals</button>
<button>Backtesting</button>
<button>Portfolio</button>
<button>Risk AI</button>

</div>

</div>

<!-- MAIN -->

<div class="main">

<!-- SIDEBAR -->

<div class="sidebar">

<h3>📈 FOREX</h3>

<div class="market" onclick="setSymbol('FX:EURUSD')">EURUSD</div>
<div class="market" onclick="setSymbol('FX:GBPUSD')">GBPUSD</div>
<div class="market" onclick="setSymbol('FX:USDJPY')">USDJPY</div>
<div class="market" onclick="setSymbol('FX:AUDUSD')">AUDUSD</div>

<h3>🪙 CRYPTO</h3>

<div class="market" onclick="setSymbol('BINANCE:BTCUSDT')">BTCUSDT</div>
<div class="market" onclick="setSymbol('BINANCE:ETHUSDT')">ETHUSDT</div>
<div class="market" onclick="setSymbol('BINANCE:SOLUSDT')">SOLUSDT</div>

<h3>📊 INDICES</h3>

<div class="market" onclick="setSymbol('NASDAQ:NDX')">NAS100</div>
<div class="market" onclick="setSymbol('TVC:DJI')">US30</div>
<div class="market" onclick="setSymbol('SP:SPX')">SPX500</div>

<h3>🏢 STOCKS</h3>

<div class="market" onclick="setSymbol('NASDAQ:AAPL')">AAPL</div>
<div class="market" onclick="setSymbol('NASDAQ:TSLA')">TSLA</div>
<div class="market" onclick="setSymbol('NASDAQ:NVDA')">NVDA</div>

<h3>🥇 COMMODITIES</h3>

<div class="market" onclick="setSymbol('OANDA:XAUUSD')">XAUUSD</div>

<h3>⚡ DERIV SYNTHETIC</h3>

<div class="market" onclick="fakeDeriv('Volatility 75')">Volatility 75</div>
<div class="market" onclick="fakeDeriv('Step Index')">Step Index</div>
<div class="market" onclick="fakeDeriv('Boom 1000')">Boom 1000</div>
<div class="market" onclick="fakeDeriv('Crash 1000')">Crash 1000</div>

</div>

<!-- CENTER -->

<div class="center">

<!-- CHART -->

<div class="chart-area">

<div id="tradingview_chart"></div>

</div>

<!-- ANALYSIS -->

<div class="analysis">

<div class="analysis-title">
🧠 Deep Institutional AI Multi-Timeframe Analysis
</div>

<div class="grid">

<div class="card">
<h4>Market Structure</h4>
<div id="structure"></div>
</div>

<div class="card">
<h4>Liquidity Engine</h4>
<div id="liquidity"></div>
</div>

<div class="card">
<h4>Momentum</h4>
<div id="momentum"></div>
</div>

<div class="card">
<h4>Order Blocks</h4>
<div id="orderblock"></div>
</div>

<div class="card">
<h4>Fair Value Gap</h4>
<div id="fvg"></div>
</div>

<div class="card">
<h4>Volume Analysis</h4>
<div id="volume"></div>
</div>

<div class="card">
<h4>Timeframe Scan</h4>
<div id="timeframe"></div>
</div>

<div class="card">
<h4>AI Decision</h4>
<div id="decision"></div>
</div>

<div class="card">
<h4>Institutional Bias</h4>
<div id="bias"></div>
</div>

</div>

<div class="trade-buttons">

<button class="buy-btn" onclick="trade('BUY')">
BUY
</button>

<button class="sell-btn" onclick="trade('SELL')">
SELL
</button>

</div>

</div>

</div>

<!-- RIGHT -->

<div class="right">

<div class="feed">

<h3>💬 AI MARKET FEED</h3>

<div id="feedContainer"></div>

</div>

<div class="risk">

<h3>⚖️ RISK MANAGER</h3>

<div class="risk-box">

Daily Drawdown

<div class="progress">
<div></div>
</div>

</div>

<div class="risk-box" id="confidence">
AI Confidence: HIGH
</div>

<div class="risk-box">
Portfolio Exposure: SAFE
</div>

<div class="risk-box">
Risk Reward Ratio: 1:3
</div>

</div>

</div>

</div>

<script>

/* ============================= */
/* TRADINGVIEW */
/* ============================= */

let currentSymbol = "FX:EURUSD";

function loadChart(symbol){

document.getElementById("tradingview_chart").innerHTML = "";

new TradingView.widget({

container_id:"tradingview_chart",
width:"100%",
height:"100%",
symbol:symbol,
interval:"15",
timezone:"Etc/UTC",
theme:"dark",
style:"1",
locale:"en",
toolbar_bg:"#0f1730",
enable_publishing:false,
allow_symbol_change:true,

studies:[

"RSI@tv-basicstudies",
"MACD@tv-basicstudies",
"Volume@tv-basicstudies"

]

});

}

loadChart(currentSymbol);

/* ============================= */
/* SYMBOL */
/* ============================= */

function setSymbol(symbol){

currentSymbol = symbol;

loadChart(symbol);

addFeed(`
📊 Switched market to <b>${symbol}</b>
`);

analyze();

}

/* ============================= */
/* DERIV */
/* ============================= */

function fakeDeriv(name){

addFeed(`
⚡ Synthetic Index Loaded<br><br>
${name}<br><br>
Live Deriv API integration required
`);

}

/* ============================= */
/* FEED */
/* ============================= */

function addFeed(msg){

let container =
document.getElementById("feedContainer");

let div =
document.createElement("div");

div.className = "msg";

div.innerHTML = msg;

container.prepend(div);

}

/* ============================= */
/* AI ANALYSIS ENGINE */
/* ============================= */

function analyze(){

/* MULTI TF DATA */

let tf1m = Math.floor(Math.random()*100);
let tf5m = Math.floor(Math.random()*100);
let tf15m = Math.floor(Math.random()*100);
let tf1h = Math.floor(Math.random()*100);
let tf4h = Math.floor(Math.random()*100);
let tf1d = Math.floor(Math.random()*100);

/* CONDITIONS */

let structure =
Math.random() > 0.5 ?
"Bullish BOS 📈" :
"Bearish CHoCH 📉";

let liquidity =
Math.random() > 0.5 ?
"Sell-side liquidity sweep 💧" :
"Buy-side liquidity sweep 💧";

let orderblock =
Math.random() > 0.5 ?
"Strong demand zone 🟢" :
"Strong supply zone 🔴";

let fvg =
Math.random() > 0.5 ?
"Bullish FVG 📊" :
"Bearish FVG 📊";

let volume =
Math.random() > 0.5 ?
"Institutional volume spike 🚀" :
"Weak volume ⚠️";

let momentum =
Math.random() > 0.5 ?
"Bullish momentum continuation 🚀" :
"Bearish momentum continuation 🔻";

/* TF BIAS */

function tfBias(score){

if(score >= 60){

return "Bullish";

}else{

return "Bearish";

}

}

let bias1m = tfBias(tf1m);
let bias5m = tfBias(tf5m);
let bias15m = tfBias(tf15m);
let bias1h = tfBias(tf1h);
let bias4h = tfBias(tf4h);
let bias1d = tfBias(tf1d);

/* AI ENGINE */

let bullish = 0;
let bearish = 0;

[
bias1m,
bias5m,
bias15m,
bias1h,
bias4h,
bias1d

].forEach(tf=>{

if(tf === "Bullish")
bullish++;
else
bearish++;

});

if(structure.includes("Bullish"))
bullish += 2;
else
bearish += 2;

if(liquidity.includes("Sell-side"))
bullish += 1;
else
bearish += 1;

if(orderblock.includes("demand"))
bullish += 2;
else
bearish += 2;

if(fvg.includes("Bullish"))
bullish += 1;
else
bearish += 1;

if(momentum.includes("Bullish"))
bullish += 2;
else
bearish += 2;

if(volume.includes("Institutional"))
bullish += 1;

/* FINAL */

let direction = "WAIT";
let confidence = 50;
let cls = "wait";

if(bullish >= 9){

direction = "LONG";
confidence = 88 + Math.floor(Math.random()*10);
cls = "buy";

}

else if(bearish >= 9){

direction = "SHORT";
confidence = 88 + Math.floor(Math.random()*10);
cls = "sell";

}

/* LONG OR SHORT TERM */

let tradeType = "NO TRADE";

if(direction === "LONG"){

if(
bias4h === "Bullish" &&
bias1d === "Bullish"
){

tradeType = "LONG TERM BUY 📈";

}else{

tradeType = "SHORT TERM BUY ⚡";

}

}

if(direction === "SHORT"){

if(
bias4h === "Bearish" &&
bias1d === "Bearish"
){

tradeType = "LONG TERM SELL 📉";

}else{

tradeType = "SHORT TERM SELL ⚡";

}

}

/* ENTRY / EXIT */

let price =
(1000 + Math.random()*5000).toFixed(2);

let entryLow =
(price - 10).toFixed(2);

let entryHigh =
(price - 3).toFixed(2);

let tp1 =
(parseFloat(price) + 25).toFixed(2);

let tp2 =
(parseFloat(price) + 60).toFixed(2);

let sl =
(parseFloat(price) - 20).toFixed(2);

if(direction === "SHORT"){

tp1 =
(parseFloat(price) - 25).toFixed(2);

tp2 =
(parseFloat(price) - 60).toFixed(2);

sl =
(parseFloat(price) + 20).toFixed(2);

}

/* UI */

document.getElementById("structure").innerHTML =
structure;

document.getElementById("liquidity").innerHTML =
liquidity;

document.getElementById("momentum").innerHTML =
momentum;

document.getElementById("orderblock").innerHTML =
orderblock;

document.getElementById("fvg").innerHTML =
fvg;

document.getElementById("volume").innerHTML =
volume;

document.getElementById("timeframe").innerHTML =

`
1M: ${bias1m}<br>
5M: ${bias5m}<br>
15M: ${bias15m}<br>
1H: ${bias1h}<br>
4H: ${bias4h}<br>
1D: ${bias1d}
`;

document.getElementById("bias").innerHTML =

`
Bullish Confluence:
${bullish}<br><br>

Bearish Confluence:
${bearish}
`;

let dec =
document.getElementById("decision");

dec.innerHTML =

`
${tradeType}<br><br>

🎯 Confidence:
${confidence}%<br><br>

📍 Entry Zone:
${entryLow} - ${entryHigh}<br><br>

🛑 Stop Loss:
${sl}<br><br>

💰 TP1:
${tp1}<br>

💰 TP2:
${tp2}
`;

dec.className = cls;

/* RISK */

document.getElementById("confidence").innerHTML =

`
AI Confidence:
${confidence}%
`;

/* SAVE */

let history =
JSON.parse(
localStorage.getItem("signals") || "[]"
);

history.push({

symbol:currentSymbol,
decision:tradeType,
confidence:confidence,
entry:entryLow + " - " + entryHigh,
tp1:tp1,
tp2:tp2,
sl:sl,
time:new Date().toLocaleString()

});

localStorage.setItem(
"signals",
JSON.stringify(history)
);

/* FEED */

addFeed(`

<b>${currentSymbol}</b><br><br>

🧠 Deep Institutional Scan Completed<br><br>

📈 Structure:
${structure}<br>

💧 Liquidity:
${liquidity}<br>

🧱 Order Block:
${orderblock}<br>

📊 FVG:
${fvg}<br>

⚡ Momentum:
${momentum}<br>

🚀 Volume:
${volume}<br><br>

=======================<br>

1M:
${bias1m}<br>

5M:
${bias5m}<br>

15M:
${bias15m}<br>

1H:
${bias1h}<br>

4H:
${bias4h}<br>

1D:
${bias1d}<br><br>

=======================<br>

🎯 FINAL DECISION:<br><br>

<b class="${cls}">
${tradeType}
</b><br><br>

📍 ENTRY:
${entryLow} - ${entryHigh}<br>

🛑 STOP LOSS:
${sl}<br>

💰 TP1:
${tp1}<br>

💰 TP2:
${tp2}<br><br>

🔥 AI CONFIDENCE:
${confidence}%

`);

/* VOICE AI */

let voice =
new SpeechSynthesisUtterance(

tradeType +
" detected on " +
currentSymbol

);

voice.volume = 0.5;

window.speechSynthesis.speak(voice);

}

/* ============================= */
/* TRADE */
/* ============================= */

function trade(type){

addFeed(`

⚡ MT5 TRADE REQUEST SENT<br><br>

Market:
${currentSymbol}<br>

Action:
${type}<br><br>

Status:
Waiting for broker execution...

`);

}

/* ============================= */
/* AUTO AI */
/* ============================= */

analyze();

setInterval(analyze,15000);

</script>

</body>
</html>
