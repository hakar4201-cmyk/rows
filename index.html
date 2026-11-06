
<!DOCTYPE html>
<html lang="ckb" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>دروستکردنی گروپ</title>
<style>
:root{--bg:#f3f5f7;--s:#fff;--t:#14202b;--m:#64748b;--l:#d5dde4;--a:#0f6b5c;--e:#b3261e}
@media(prefers-color-scheme:dark){:root{--bg:#0e151b;--s:#16212a;--t:#e8eef3;--m:#93a4b3;--l:#2a3a47;--a:#3cc4a8;--e:#ff8a80}}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--t);font-family:Tahoma,sans-serif}
main{max-width:520px;margin:auto;padding:12px}
.c{background:var(--s);border:1px solid var(--l);border-radius:12px;padding:12px;margin-bottom:10px}
label{display:block;margin-bottom:6px;font-weight:bold}
textarea{width:100%;font:inherit;padding:10px;border:1px solid var(--l);border-radius:8px;background:var(--bg);color:var(--t);direction:ltr;text-align:left;min-height:85px;resize:vertical}
button{font:inherit;cursor:pointer;border-radius:8px;border:1px solid var(--l);background:var(--bg);color:var(--t);touch-action:manipulation}
.main{width:100%;background:var(--a);color:white;border:0;padding:11px;font-weight:bold;margin-top:10px}
.counter{display:flex;align-items:center;gap:12px;direction:ltr}
.counter button{width:42px;height:38px;font-size:1.3rem}
.counter b{min-width:30px;text-align:center;font-size:1.2rem}
.err{color:var(--e);font-size:.9rem;margin-top:8px}
.info{display:flex;justify-content:space-between;color:var(--m);font-size:.75rem;margin-top:8px}
.total{font-size:.8rem;color:var(--m);text-align:center}
.rows{display:grid;grid-template-columns:repeat(4,1fr);gap:7px;margin-top:10px}
.rb{padding:11px 3px;font-size:.9rem;user-select:none;-webkit-user-select:none}
.rb.on{background:var(--a);color:white;border-color:var(--a)}
.rb:active{opacity:.7}
.selected{direction:ltr;text-align:center;font-family:monospace;font-size:1.5rem;font-weight:bold;padding:20px 5px;word-break:break-word}
.hint{text-align:center;color:var(--m);font-size:.8rem;padding:10px}
.empty{text-align:center;color:var(--m);padding:15px}
</style>
</head>
<body>
<main>

<div class="c">
<label>ناوی کەسەکان</label>
<textarea id="names">A,B,C,D,E,F,G,H,I,J,K,L,M,N,O</textarea>

<label style="margin-top:12px">ژمارەی کەسی هەر گروپ</label>
<div class="counter">
<button id="minus">−</button>
<b id="k">3</b>
<button id="plus">+</button>
</div>

<button class="main" id="generate">دروستکردنی گروپەکان</button>
<div class="err" id="err"></div>

<div class="info">
<span>کەسان: <b id="people">15</b></span>
<span>کۆی گروپەکان: <b id="total">0</b></span>
</div>
</div>

<div class="c">
<div class="total">لیستی گروپەکان</div>
<div class="rows" id="rows"></div>
<div class="hint">کلیک: بینینی گروپ | دەست ڕاگرتن: سڕینەوە</div>
</div>

<div class="c">
<div class="total" id="number">گروپێک هەڵبژێرە</div>
<div class="selected" id="selected">—</div>
</div>

</main>

<script>
const $=id=>document.getElementById(id);

let k=3;
let result=[];
let selected=null;
let pressTimer=null;
let longPress=false;
let pointerStart=null;

function generate(){
const n=$('names').value.split(/[,،\n]/).map(x=>x.trim()).filter(Boolean);

$('err').textContent='';

if(new Set(n).size!==n.length){
$('err').textContent='ناوی دووبارە هەیە.';
return;
}

if(k<2||k>n.length){
$('err').textContent='ژمارەی کەسی گروپ هەڵەیە.';
return;
}

result=[];
selected=null;

let combinations=[];

function make(start,group){
if(group.length===k){
combinations.push([...group]);
return;
}
for(let i=start;i<n.length;i++){
group.push(n[i]);
make(i+1,group);
group.pop();
}
}

make(0,[]);

for(let i=combinations.length-1;i>0;i--){
let j=Math.floor(Math.random()*(i+1));
[combinations[i],combinations[j]]=
[combinations[j],combinations[i]];
}

for(let g of combinations){
if(result.every(x=>
x.filter(v=>g.includes(v)).length<=1
)){
result.push(g);
}
}

$('people').textContent=n.length;
renderRows();
showSelected();
}

function renderRows(){
$('total').textContent=result.length;

$('rows').innerHTML=result.length?
result.map((g,i)=>
`<button class="rb ${selected===i?'on':''}" data-i="${i}">${i+1}</button>`
).join('')
:'<div class="empty">هیچ گروپێک نییە</div>';
}

function showSelected(){
if(selected===null||!result[selected]){
$('number').textContent='گروپێک هەڵبژێرە';
$('selected').textContent='—';
return;
}

$('number').textContent='گروپی ژمارە '+(selected+1);
$('selected').textContent='('+result[selected].join(', ')+')';
}

function deleteGroup(i){
if(!result[i])return;

if(!confirm('ئایا دڵنیایت لە سڕینەوەی گروپی '+(i+1)+'؟')){
return;
}

result.splice(i,1);
selected=null;
renderRows();
showSelected();
}

$('rows').onpointerdown=e=>{
const b=e.target.closest('.rb');
if(!b)return;

longPress=false;
pointerStart=b;
const i=Number(b.dataset.i);

pressTimer=setTimeout(()=>{
longPress=true;
deleteGroup(i);
},700);
};

function cancelPress(){
clearTimeout(pressTimer);
}

$('rows').onpointerup=cancelPress;
$('rows').onpointerleave=cancelPress;
$('rows').onpointercancel=cancelPress;

$('rows').onclick=e=>{
const b=e.target.closest('.rb');
if(!b)return;

if(longPress){
longPress=false;
return;
}

selected=Number(b.dataset.i);
renderRows();
showSelected();
};

$('minus').onclick=()=>{
if(k>2){
k--;
$('k').textContent=k;
}
};

$('plus').onclick=()=>{
k++;
$('k').textContent=k;
};

$('generate').onclick=generate;

generate();
</script>
</body>
</html>
