<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hari Om Enterprises – Daily Stock Register</title>

<style>
*{box-sizing:border-box;}

body{
    font-family:Arial,sans-serif;
    background:#f2f4f7;
    margin:0;
    padding:6px;
}

h2,h3{
    text-align:center;
    margin:3px 0;
}

.report-info{
    text-align:center;
    font-weight:bold;
    margin:4px 0;
    color:#333;
}

.date-box{
    text-align:center;
    margin:4px 0;
}

input[type="date"],select{
    padding:6px;
    font-size:14px;
    width:160px;
    border-radius:6px;
    border:1px solid #ccc;
}

/* Table */
.table-wrapper{
    width:100%;
    overflow-x:hidden;
}

table{
    width:100%;
    border-collapse:collapse;
    background:#fff;
    table-layout:fixed;
    font-size:12px;
}

th,td{
    border:1px solid #ccc;
    padding:4px 2px;
    text-align:center;
    word-wrap:break-word;
}

th{
    background:#b83db8;
    color:#fff;
    font-size:11px;
}

td.sno{width:30px;font-weight:bold;}
td.item{text-align:left;font-size:11px;padding-left:4px;}

input[type="number"]{
    width:100%;
    padding:3px;
    border:none;
    text-align:center;
    font-size:12px;
}

.total-row{
    background:#cfe9f0;
    font-weight:bold;
}

/* Buttons */
button{
    width:100%;
    padding:11px;
    margin-top:8px;
    font-size:14px;
    border-radius:8px;
    border:none;
    cursor:pointer;
    color:#fff;
    font-weight:bold;
}

.btn-add{background:#6f42c1;}
.btn-next{background:#20c997;}
.btn-clear{background:#dc3545;}
.btn-print{background:#0d6efd;}
button:active{transform:scale(0.97);}

/* Popup */
.popup-overlay{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,0.45);
    display:none;
    align-items:center;
    justify-content:center;
    z-index:999;
}

.popup-box{
    background:#fff;
    width:260px;
    border-radius:12px;
    padding:16px;
    text-align:center;
}

.popup-actions{
    display:flex;
    gap:10px;
}

.btn-no{background:#eee;color:#000;}
.btn-yes{background:#ff5c5c;color:#fff;}

/* Small phones */
@media(max-width:360px){
    table{font-size:10px;}
    th{font-size:10px;}
    td.item{font-size:10px;}
}

/* Print */
@media print{
    body{padding:2px;background:#fff;}
    button,select{display:none;}
    h2{font-size:16px;}
    h3{font-size:13px;}
    table{font-size:10px;}
    th,td{padding:3px 2px;}
    input{border:none;font-size:10px;}
}
</style>

<script>
let items = JSON.parse(localStorage.getItem("items")) || [
"1 LTR WATER","500ML WATER","200ML COLA","200ML ORANGE","200ML LEMON","200ML POWER UP",
"500ML COLA","500ML ORANGE","500ML LEMON","500ML POWER UP",
"1 LTR COLA","1 LTR ORANGE","1 LTR POWER UP","1 LTR LEMON",
"SUNCRUSH ORANGE","SUNCRUSH MIX FRUIT","SUNCRUSH MANGO",
"150ML NIMBU PANI","150ML APPLE","150ML MIX FRUIT","150ML SPINNER ORANGE",
"150ML SPINNER BLUE","150ML GLUCOSE ENERGY","500ML GLUCOSE ENERGY",
"150ML BERRY KIK","250ML BERRY KIK","500ML MANGO",
"330ML GOLD BOOST","185ML GOLD BOOST","185ML COLA CAN",
"185ML ORANGE CAN","185ML LEMON CAN",
"MILK SHAKE CHOCOLATE","MILK SHAKE VANILLA",
"150ML JEERA","500ML JEERA","150ML MANGO",
"150ML ORANGE KIK","COCONUT WATER","500ML SODA"
];

let data={},pressTimer=null,confirmAction=null;
let currentTruck=localStorage.getItem("currentTruck")||"Truck 1";

function getTruckKey(){return "data_"+currentTruck.replace(" ","");}
function loadTruckData(){data=JSON.parse(localStorage.getItem(getTruckKey()))||{};}

function save(){
    localStorage.setItem("items",JSON.stringify(items));
    localStorage.setItem(getTruckKey(),JSON.stringify(data));
}

function switchTruck(){
    currentTruck=document.getElementById("truck").value;
    localStorage.setItem("currentTruck",currentTruck);
    location.reload();
}

/* Popup */
function showPopup(msg,yes){
    document.getElementById("popupMsg").innerText=msg;
    document.getElementById("popup").style.display="flex";
    confirmAction=yes;
}
function popupYes(){document.getElementById("popup").style.display="none";if(confirmAction)confirmAction();}
function popupNo(){document.getElementById("popup").style.display="none";confirmAction=null;}

/* Core */
function calc(i){
    let s=+document.getElementById("s"+i).value||0;
    let l=+document.getElementById("l"+i).value||0;
    let sa=+document.getElementById("sa"+i).value||0;
    let t=s+l;
    document.getElementById("t"+i).innerText=t.toFixed(1);
    document.getElementById("ls"+i).innerText=(t-sa).toFixed(1);
    data[i]={s,l,sa};
    save(); calcTotals();
}

function calcTotals(){
    let TSv=0,TLv=0,TTv=0,TSAv=0,TLSv=0;
    items.forEach((_,i)=>{
        let s=data[i]?.s||0,l=data[i]?.l||0,sa=data[i]?.sa||0,t=s+l;
        TSv+=s; TLv+=l; TTv+=t; TSAv+=sa; TLSv+=(t-sa);
    });
    TS.innerText=TSv.toFixed(1);
    TL.innerText=TLv.toFixed(1);
    TT.innerText=TTv.toFixed(1);
    TSA.innerText=TSAv.toFixed(1);
    TLS.innerText=TLSv.toFixed(1);
}

/* Actions */
function carryForward(){
    showPopup("Carry forward to next day?",()=>{
        items.forEach((_,i)=>{
            let t=(data[i]?.s||0)+(data[i]?.l||0);
            let ls=t-(data[i]?.sa||0);
            data[i]={s:ls,l:0,sa:0};
        });
        save(); location.reload();
    });
}

function clearData(){
    showPopup("Clear all entered data?",()=>{
        data={}; save(); location.reload();
    });
}

function addItem(){
    let n=prompt("Enter item name"); if(!n)return;
    items.push(n.toUpperCase()); save(); location.reload();
}

function printReport(){window.print();}

/* Delete */
function startPress(i){
    pressTimer=setTimeout(()=>{
        showPopup("Delete this item permanently?",()=>{
            items.splice(i,1);
            let newData={};
            items.forEach((_,idx)=>newData[idx]=data[idx<i?idx:idx+1]);
            data=newData; save(); location.reload();
        });
    },900);
}
function cancelPress(){clearTimeout(pressTimer);}

/* Init */
window.onload=()=>{
    document.getElementById("truck").value=currentTruck;
    loadTruckData();
    let body=document.getElementById("body");
    items.forEach((name,i)=>{
        let r=body.insertRow();
        r.innerHTML=`
        <td class="sno">${i+1}</td>
        <td class="item"
        ontouchstart="startPress(${i})" ontouchend="cancelPress()"
        onmousedown="startPress(${i})" onmouseup="cancelPress()">${name}</td>
        <td><input type="number" inputmode="numeric" id="s${i}" value="${data[i]?.s||""}" oninput="calc(${i})"></td>
        <td><input type="number" inputmode="numeric" id="l${i}" value="${data[i]?.l||""}" oninput="calc(${i})"></td>
        <td id="t${i}"></td>
        <td><input type="number" inputmode="numeric" id="sa${i}" value="${data[i]?.sa||""}" oninput="calc(${i})"></td>
        <td id="ls${i}"></td>`;
        calc(i);
    });
};
</script>
</head>

<body>

<h2>HARI OM ENTERPRISES</h2>
<h3>Daily Stock Register</h3>

<div class="date-box">
Date:
<input id="date" type="date" onchange="localStorage.setItem('date',this.value)">
</div>

<div class="report-info">Vehicle</div>

<div class="date-box">
<select id="truck" onchange="switchTruck()">
<option>Truck 1</option>
<option>Truck 2</option>
<option>Truck 3</option>
<option>Truck 4</option>
</select>
</div>

<div class="table-wrapper">
<table>
<tr>
<th>S.NO.</th>
<th>ITEM</th>
<th>STOCK</th>
<th>LOAD</th>
<th>TOTAL</th>
<th>SALES</th>
<th>LEFT STOCK</th>
</tr>

<tbody id="body"></tbody>

<tr class="total-row">
<td colspan="2">TOTAL</td>
<td id="TS"></td>
<td id="TL"></td>
<td id="TT"></td>
<td id="TSA"></td>
<td id="TLS"></td>
</tr>
</table>
</div>

<button class="btn-add" onclick="addItem()">➕ Add Item</button>
<button class="btn-next" onclick="carryForward()">🔁 Next Day – Carry Forward</button>
<button class="btn-clear" onclick="clearData()">🧹 Clear Data</button>
<button class="btn-print" onclick="printReport()">🖨 Save as PDF / Print</button>

<div class="popup-overlay" id="popup">
<div class="popup-box">
<h4 id="popupMsg"></h4>
<div class="popup-actions">
<button class="btn-no" onclick="popupNo()">No</button>
<button class="btn-yes" onclick="popupYes()">Yes</button>
</div>
</div>
</div>

</body>
</html>
