<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>학년별 운동 스케줄표</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#f3f6f1;--surface:#fff;--ink:#1d2a22;--muted:#5d6b62;--line:#d5ddd3;--accent:#1f6b4a;--accent-ink:#fff;--warn:#b3261e;--off:#e9ece8;
  --chip-s:55%;--chip-l:90%;--chip-ink-l:20%;
  box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px);
  color-scheme:light;
}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){
  --bg:#141a16;--surface:#1c241f;--ink:#e7eee9;--muted:#9fb0a5;--line:#33403a;--accent:#6fd0a0;--accent-ink:#0f1f17;--warn:#ff8a80;--off:#252d28;
  --chip-s:30%;--chip-l:24%;--chip-ink-l:90%;color-scheme:dark;}}
:root[data-theme="dark"]{
  --bg:#141a16;--surface:#1c241f;--ink:#e7eee9;--muted:#9fb0a5;--line:#33403a;--accent:#6fd0a0;--accent-ink:#0f1f17;--warn:#ff8a80;--off:#252d28;
  --chip-s:30%;--chip-l:24%;--chip-ink-l:90%;color-scheme:dark;}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);font-family:'Noto Sans KR',-apple-system,'Apple SD Gothic Neo','Malgun Gothic',sans-serif;line-height:1.5}
main{max-width:1100px;margin:0 auto;padding:20px 16px 48px}
h1{font-size:1.5rem;margin:0 0 4px}
.sub{color:var(--muted);margin:0 0 20px;font-size:.92rem}
.panel{background:var(--surface);border:1px solid var(--line);border-radius:10px;padding:16px;margin-bottom:16px}
.panel h2{font-size:1rem;margin:0 0 12px}
.row{display:flex;flex-wrap:wrap;gap:12px;align-items:flex-end}
label{display:flex;flex-direction:column;font-size:.82rem;color:var(--muted);gap:4px}
select,input[type=time],input[type=text],input[type=number]{font:inherit;color:var(--ink);background:var(--bg);border:1px solid var(--line);border-radius:6px;padding:7px 9px;min-height:38px}
.days{display:flex;gap:6px}
.days label{flex-direction:row;align-items:center;gap:4px;border:1px solid var(--line);border-radius:6px;padding:7px 10px;color:var(--ink);cursor:pointer;background:var(--bg);min-height:38px}
.days input:checked+span{font-weight:700;color:var(--accent)}
button{font:inherit;cursor:pointer;border-radius:6px;border:1px solid var(--line);background:var(--surface);color:var(--ink);padding:7px 14px;min-height:38px}
button.primary{background:var(--accent);color:var(--accent-ink);border-color:var(--accent);font-weight:700}
button:focus-visible,select:focus-visible,input:focus-visible{outline:2px solid var(--accent);outline-offset:2px}
.rules{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px}
.rule{display:flex;gap:8px;align-items:center;border-radius:6px;padding:5px 6px 5px 10px;font-size:.85rem;background:hsl(var(--h) var(--chip-s) var(--chip-l));color:hsl(var(--h) 40% var(--chip-ink-l))}
.rule button{min-height:24px;padding:0 7px;border:none;background:transparent;color:inherit;font-size:1rem}
.bar{display:flex;flex-wrap:wrap;gap:10px;align-items:center;justify-content:space-between;margin-bottom:12px}
.nav{display:flex;gap:8px;align-items:center}
.nav strong{font-size:1.25rem;min-width:7.5em;text-align:center}
.wrap{overflow-x:auto;border:1px solid var(--line);border-radius:10px;background:var(--surface)}
table{border-collapse:collapse;width:100%;min-width:980px;table-layout:fixed}
th{padding:8px;border-bottom:1px solid var(--line);font-size:.9rem}
td{vertical-align:top;border:1px solid var(--line);border-top:none;padding:6px;height:110px}
td:first-child{border-left:none}td:last-child{border-right:none}
td.empty{background:var(--bg)}
td.off{background:var(--off)}
.dnum{display:flex;justify-content:space-between;align-items:center;margin-bottom:4px;font-weight:700;font-size:.9rem}
.dnum button{min-height:22px;padding:0 6px;font-size:.7rem;color:var(--muted);font-weight:400}
.chip{border-radius:5px;padding:3px 6px;margin-bottom:4px;font-size:.78rem;line-height:1.35;background:hsl(var(--h) var(--chip-s) var(--chip-l));color:hsl(var(--h) 40% var(--chip-ink-l))}
.chip b{font-weight:700}
.chip.clash{outline:2px solid var(--warn)}
.offtag{color:var(--muted);font-size:.8rem}
.legend{display:flex;flex-wrap:wrap;gap:8px;align-items:center;font-size:1rem;color:var(--muted)}
.legend .rule{padding:8px 18px;font-size:1.05rem;min-height:44px;display:inline-flex;align-items:center;cursor:pointer;border:2px solid transparent}
.legend .rule[aria-pressed=true]{border-color:var(--ink)}
.note{color:var(--muted);font-size:.82rem;margin-top:10px}
#list{display:none}
.litem{background:var(--surface);border:1px solid var(--line);border-radius:10px;padding:10px 12px;margin-bottom:8px}
.litem.off{background:var(--off)}
.lhead{display:flex;justify-content:space-between;align-items:center;margin-bottom:6px}
.litem .offtag{margin:0}
@media (max-width:700px){
  .wrap{display:none}
  #list{display:block}
  main{padding:14px 10px 40px}
  button,select,input[type=time],input[type=text]{min-height:46px;font-size:1rem}
  .days label{min-height:46px;padding:8px 14px;font-size:1rem}
  .days{flex-wrap:wrap}
  .legend .rule{min-height:48px;padding:8px 20px;font-size:1.1rem}
  .rule{font-size:.95rem}
  .rule button{min-height:34px;min-width:34px}
  .chip{font-size:.95rem;padding:5px 8px}
  .nav strong{font-size:1.1rem;min-width:6em}
}
@media print{#list{display:none!important}.wrap{display:block!important}
  body{background:#fff;color:#000}.panel,.noprint{display:none}main{padding:0}
  .wrap{border:none;overflow:visible}td{height:90px}
}
</style>
</head>
<body>
<main>
  <h1>학년별 운동 스케줄표</h1>
  <p class="sub">학년·요일·시간·장소를 추가하면 월별 표가 자동으로 만들어집니다.</p>

  <section class="panel noprint">
    <h2>운동 일정 추가</h2>
    <div class="row">
      <div><div style="font-size:.82rem;color:var(--muted);margin-bottom:4px">학년 (여러 개 선택 가능)</div><div class="days" id="grades"></div></div>
      <div>
        <div style="font-size:.82rem;color:var(--muted);margin-bottom:4px">요일 (여러 개 선택 가능)</div>
        <div class="days" id="days"></div>
      </div>
      <label>적용 주차 <select id="week"><option value="0">매주</option><option value="1">1째주</option><option value="2">2째주</option><option value="3">3째주</option><option value="4">4째주</option><option value="5">5째주</option></select></label>
      <label>시작 시간 <span style="display:flex;gap:8px;align-items:center"><input type="checkbox" id="useStart" checked aria-label="시작 시간 사용"><input type="time" id="start" value="09:00"></span></label>
      <label>끝나는 시간 <span style="display:flex;gap:8px;align-items:center"><input type="checkbox" id="useEnd" checked aria-label="끝나는 시간 사용"><input type="time" id="end" value="09:40"></span></label>
      <label>장소 <input type="text" id="place" placeholder="예: 체육관" style="width:150px"></label>
      <button class="primary" id="add">일정 추가</button>
    </div>
    <div class="note" id="msg" role="status"></div>
    <div class="rules" id="rules"></div>
  </section>

  <div class="bar noprint">
    <div class="nav">
      <button id="prev" aria-label="이전 달">◀</button>
      <strong id="title"></strong>
      <button id="next" aria-label="다음 달">▶</button>
      <button id="today">이번 달</button>
    </div>
    <div class="row">
      <button id="print">인쇄</button>
    </div>
  </div>
  <div class="legend noprint" id="legend" style="margin-bottom:10px"></div>

  <div class="wrap"><table id="cal"></table></div>
  <div id="list"></div>
  <p class="note noprint">‘적용 주차’를 고르면 그 주(예: 2째주 수요일)만 다르게 설정할 수 있고, 같은 학년·요일의 ‘매주’ 일정보다 우선 적용돼요. 날짜 옆 ‘휴무’ 버튼을 누르면 그날(공휴일·행사 등)은 운동 일정에서 빠집니다. 같은 장소에서 시간이 겹치면 빨간 테두리로 표시됩니다. 입력한 내용은 이 브라우저에 저장됩니다.</p>
</main>

<script>
(function(){
  var DAYS=['일','월','화','수','목','금','토'];
  var HUE={1:8,2:35,3:55,4:150,5:205,6:275};
  var KEY='gymSchedule.v1';
  var state={rules:[],off:{},filter:0};
  var now=new Date(),yr=now.getFullYear(),mo=now.getMonth();

  try{var s=localStorage.getItem(KEY);if(s){var p=JSON.parse(s);if(p&&p.rules){state.rules=p.rules;state.off=p.off||{};}}else{seed();}}catch(e){seed();}
  function seed(){
    state.rules=[
      {id:1,grade:1,day:1,start:'09:00',end:'09:40',place:'체육관'},
      {id:2,grade:2,day:1,start:'10:00',end:'10:40',place:'운동장'},
      {id:3,grade:3,day:2,start:'09:00',end:'09:40',place:'강당'}
    ];
  }
  function save(){try{localStorage.setItem(KEY,JSON.stringify({rules:state.rules,off:state.off}));}catch(e){}}
  var $=function(id){return document.getElementById(id)};
  function pad(n){return n<10?'0'+n:''+n}
  function tr(r){return r.start&&r.end?r.start+'–'+r.end:r.start?r.start+'~':r.end?'~'+r.end:'시간 미정'}
  function esc(t){return String(t).replace(/[&<>"]/g,function(c){return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]})}

  // day checkboxes (Mon–Fri)
  $('days').innerHTML=[1,2,3,4,5,6,0].map(function(d){return '<label><input type="checkbox" value="'+d+'"><span>'+DAYS[d]+'</span></label>'}).join('');

  $('useStart').onchange=function(){$('start').disabled=!this.checked};
  $('useEnd').onchange=function(){$('end').disabled=!this.checked};
  $('grades').innerHTML=[1,2,3,4,5,6].map(function(g){return '<label><input type="checkbox" value="'+g+'"><span>'+g+'</span></label>'}).join('');
  $('add').onclick=function(){
    var days=[].slice.call(document.querySelectorAll('#days input:checked')).map(function(i){return +i.value});
    var st=$('useStart').checked?$('start').value:'',en=$('useEnd').checked?$('end').value:'',pl=$('place').value.trim(),gs=[].slice.call(document.querySelectorAll('#grades input:checked')).map(function(i){return +i.value}),wk=+$('week').value;
    if(!gs.length){return msg('학년을 하나 이상 선택해 주세요.')}
    if(!days.length){return msg('요일을 하나 이상 선택해 주세요.')}
    if($('useEnd').checked&&!en){return msg('끝나는 시간을 입력하거나, 체크를 해제해 주세요.')}
    if($('useStart').checked&&!st){return msg('시작 시간을 입력하거나, 체크를 해제해 주세요.')}
    if(st&&en&&en<=st){return msg('끝나는 시간은 시작 시간보다 늦어야 합니다.')}
    if(!pl){return msg('장소를 입력해 주세요.')}
    days.forEach(function(d){gs.forEach(function(g){
      var dup=state.rules.some(function(r){return r.grade===g&&r.day===d&&(r.week||0)===wk&&r.start===st&&r.end===en&&r.place===pl});
      if(!dup)state.rules.push({id:Date.now()+d*10+g,grade:g,day:d,start:st,end:en,place:pl,week:wk});});
    });
    msg(gs.join('·')+'학년 일정을 추가했어요.');
    save();render();
  };
  function msg(t){$('msg').textContent=t}

  $('prev').onclick=function(){mo--;if(mo<0){mo=11;yr--}render()};
  $('next').onclick=function(){mo++;if(mo>11){mo=0;yr++}render()};
  $('today').onclick=function(){yr=now.getFullYear();mo=now.getMonth();render()};
  $('print').onclick=function(){window.print()};

  function render(){
    // rule chips
    var sorted=state.rules.slice().sort(function(a,b){return a.grade-b.grade||a.day-b.day||(a.week||0)-(b.week||0)||(a.start||a.end||'99').localeCompare(b.start||b.end||'99')});
    $('rules').innerHTML=sorted.length?sorted.map(function(r){
      return '<span class="rule" style="--h:'+HUE[r.grade]+'">'+r.grade+'학년 · '+(r.week?r.week+'째주 ':'')+DAYS[r.day]+' '+tr(r)+' · '+esc(r.place)+
        '<button data-del="'+r.id+'" aria-label="삭제">×</button></span>';
    }).join(''):'<span class="note">아직 추가된 일정이 없습니다.</span>';

    // legend / grade filter
    var lg='<span>학년 보기:</span><span class="rule" style="--h:150" role="button" tabindex="0" data-f="0" aria-pressed="'+(state.filter===0)+'">전체</span>';
    for(var g=1;g<=6;g++)lg+='<span class="rule" style="--h:'+HUE[g]+'" role="button" tabindex="0" data-f="'+g+'" aria-pressed="'+(state.filter===g)+'">'+g+'학년</span>';
    $('legend').innerHTML=lg;

    $('title').textContent=yr+'년 '+(mo+1)+'월';

    // calendar (Sun–Sat)
    var last=new Date(yr,mo+1,0).getDate();
    var html='<thead><tr>'+[0,1,2,3,4,5,6].map(function(d){return '<th>'+DAYS[d]+'</th>'}).join('')+'</tr></thead><tbody>';
    var row=null,hasAny=false,lhtml='';
    for(var d=1;d<=last;d++){
      var dt=new Date(yr,mo,d),wd=dt.getDay();
      if(row===null||wd===0){
        if(row!==null)html+='</tr>';
        html+='<tr>';row=0;
        for(var k=0;k<wd;k++)html+='<td class="empty"></td>'; // leading blanks for first week
      }
      var key=yr+'-'+pad(mo+1)+'-'+pad(d),off=!!state.off[key];
      var nth=Math.ceil(d/7);
      var active=state.rules.filter(function(r){return r.day===wd&&(!r.week||r.week===nth)}).filter(function(r,i,arr){return r.week||!arr.some(function(o){return o.grade===r.grade&&o.week===nth})});
      var items=active.filter(function(r){return !state.filter||r.grade===state.filter})
        .sort(function(a,b){return (a.start||a.end||'99').localeCompare(b.start||b.end||'99')||a.grade-b.grade});
      var body='';
      if(off){body='<div class="offtag">휴무</div>'}
      else items.forEach(function(r){
        var clash=active.some(function(o){return o!==r&&o.place===r.place&&o.start&&r.start&&o.end&&r.end&&o.start<r.end&&r.start<o.end});
        body+='<div class="chip'+(clash?' clash':'')+'" style="--h:'+HUE[r.grade]+'"'+(clash?' title="같은 장소에서 시간이 겹칩니다"':'')+'><b>'+r.grade+'학년</b> '+tr(r)+'<br>'+esc(r.place)+'</div>';
      });
      lhtml+='<div class="litem'+(off?' off':'')+'"><div class="lhead"><strong>'+(mo+1)+'월 '+d+'일 ('+DAYS[wd]+')</strong><button data-off="'+key+'">'+(off?'휴무 해제':'휴무')+'</button></div>'+(body||'<div class="offtag">일정 없음</div>')+'</div>';
      html+='<td class="'+(off?'off':'')+'"><div class="dnum"><span>'+d+'</span><button class="noprint" data-off="'+key+'">'+(off?'휴무 해제':'휴무')+'</button></div>'+body+'</td>';
    }
    if(row!==null){
      var lastWd=new Date(yr,mo,last).getDay();
      // pad trailing cells in last row
      var lastDay=lastWd;
      for(var q=lastDay+1;q<=6;q++)html+='<td class="empty"></td>';
      html+='</tr>';
    }
    $('cal').innerHTML=html+'</tbody>';
    $('list').innerHTML=lhtml;
  }

  document.addEventListener('click',function(e){
    var t=e.target;
    if(t.dataset.del){state.rules=state.rules.filter(function(r){return String(r.id)!==t.dataset.del});save();render();}
    else if(t.dataset.off){if(state.off[t.dataset.off])delete state.off[t.dataset.off];else state.off[t.dataset.off]=1;save();render();}
    else if(t.dataset.f!==undefined){state.filter=+t.dataset.f;render();}
  });
  document.addEventListener('keydown',function(e){
    if((e.key==='Enter'||e.key===' ')&&e.target.dataset&&e.target.dataset.f!==undefined){e.preventDefault();state.filter=+e.target.dataset.f;render();}
  });
  render();
})();
</script>
</body>
</html>
