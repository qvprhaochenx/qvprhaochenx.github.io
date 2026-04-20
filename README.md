# qvprhaochenx.github.io
<html lang="zh">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>【BU COM 学术调研】波士顿地区大学生社交媒体依赖与亲密关系连结研究</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&family=Dancing+Script:wght@700&family=Noto+Sans+SC:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --pu:#673ab7;--pul:#7e57c2;--red:#d93025;
  --border:#dadce0;--text:#202124;--sub:#5f6368;
  --bg:#f0ebf8;--card:#fff;--blue:#1a73e8;
}
html,body{width:100%;min-height:100%;font-family:'Roboto','Noto Sans SC',sans-serif}

/* ── PHASE 1 ── */
#phase1{background:var(--bg);min-height:100vh;padding:20px 0 80px;position:relative;z-index:10}
.gf-wrap{max-width:640px;margin:0 auto;padding:0 16px}

#easter-avatar{
  position:fixed;top:16px;right:16px;width:32px;height:32px;border-radius:50%;
  background:rgba(200,200,200,0.15);color:rgba(155,155,155,0.4);
  font-size:13px;font-weight:500;display:flex;align-items:center;justify-content:center;
  cursor:pointer;z-index:999;transition:background .3s;user-select:none;
  font-family:'Roboto',sans-serif;
}
#easter-avatar:hover{background:rgba(200,200,200,0.28)}

.gf-topbar{
  background:#fff;box-shadow:0 1px 3px rgba(0,0,0,.12);
  padding:0 16px;height:64px;display:flex;align-items:center;
  position:sticky;top:0;z-index:100;
}
.gf-logo{font-size:22px;color:#5f6368;font-weight:400;letter-spacing:-.5px}

.gf-title-card{
  background:var(--card);border-radius:8px;border-top:10px solid var(--pu);
  box-shadow:0 2px 1px -1px rgba(0,0,0,.2),0 1px 1px rgba(0,0,0,.14),0 1px 3px rgba(0,0,0,.12);
  padding:24px;margin-top:18px;margin-bottom:12px;
}
.gf-form-title{font-size:26px;font-weight:400;color:var(--text);line-height:1.4;margin-bottom:10px}
.gf-form-desc{font-size:14px;color:var(--sub);line-height:1.7}
.gf-req-note{font-size:13px;color:var(--sub);margin-top:10px}
.gf-req-note em{color:var(--red);font-style:normal}

.gf-card{
  background:var(--card);border-radius:8px;
  box-shadow:0 2px 1px -1px rgba(0,0,0,.2),0 1px 1px rgba(0,0,0,.14),0 1px 3px rgba(0,0,0,.12);
  padding:24px;margin-bottom:12px;position:relative;transition:box-shadow .2s;
}
.gf-card:focus-within{box-shadow:0 0 0 2px var(--pu),0 2px 4px rgba(0,0,0,.14)}
.gf-qlabel{font-size:16px;font-weight:400;color:var(--text);margin-bottom:18px;line-height:1.5}
.gf-qlabel .req{color:var(--red);margin-left:3px}

/* Likert */
.gf-likert{display:flex;align-items:center;width:100%;padding:4px 0 8px}
.gf-lside{font-size:12px;color:var(--sub);min-width:52px;flex-shrink:0;line-height:1.35}
.gf-lside.l{text-align:left;padding-right:8px}
.gf-lside.r{text-align:right;padding-left:8px}
.gf-lopts{display:flex;flex:1;justify-content:space-between;align-items:center;gap:6px}
.gf-lcol{display:flex;flex-direction:column;align-items:center;gap:6px;flex:1;cursor:pointer}
.gf-lnum{font-size:12px;color:var(--sub)}
.gf-radio{
  width:20px;height:20px;border:2px solid #757575;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  transition:border-color .2s,background .2s;position:relative;
}
.gf-lcol:hover .gf-radio{border-color:var(--pu)}
.gf-radio.sel{border-color:var(--pu);background:var(--pu)}
.gf-radio.sel::after{content:'';width:8px;height:8px;background:#fff;border-radius:50%;position:absolute}

/* Radio group */
.gf-radio-group{display:flex;flex-direction:column;gap:4px}
.gf-radio-item{display:flex;align-items:center;gap:12px;padding:10px 12px;border-radius:4px;cursor:pointer;transition:background .15s}
.gf-radio-item:hover{background:#f8f4ff}
.gf-radio-item .gf-dot{width:20px;height:20px;border:2px solid #757575;border-radius:50%;display:flex;align-items:center;justify-content:center;transition:border-color .2s,background .2s;position:relative;flex-shrink:0}
.gf-radio-item:hover .gf-dot{border-color:var(--pu)}
.gf-radio-item .gf-dot.sel{border-color:var(--pu);background:var(--pu)}
.gf-radio-item .gf-dot.sel::after{content:'';width:8px;height:8px;background:#fff;border-radius:50%;position:absolute}
.gf-radio-item span{font-size:14px;color:var(--text)}

/* Checkbox group */
.gf-checkbox-group{display:flex;flex-direction:column;gap:4px}
.gf-check-item{display:flex;align-items:center;gap:12px;padding:10px 12px;border-radius:4px;cursor:pointer;transition:background .15s}
.gf-check-item:hover{background:#f8f4ff}
.gf-checkmark{width:20px;height:20px;border:2px solid #757575;border-radius:2px;display:flex;align-items:center;justify-content:center;transition:border-color .2s,background .2s;flex-shrink:0}
.gf-check-item:hover .gf-checkmark{border-color:var(--pu)}
.gf-checkmark.sel{border-color:var(--pu);background:var(--pu)}
.gf-checkmark.sel::after{content:'✓';color:#fff;font-size:13px;line-height:1}
.gf-check-item span{font-size:14px;color:var(--text)}

/* Text inputs */
.gf-input-wrap{border-bottom:1px solid var(--border);padding-bottom:4px;transition:border-color .2s}
.gf-input-wrap:focus-within{border-bottom:2px solid var(--pu)}
.gf-input,.gf-textarea{
  width:100%;border:none;outline:none;font-size:14px;color:var(--text);
  font-family:'Roboto','Noto Sans SC',sans-serif;padding:8px 0 4px;background:transparent;resize:none;
}
.gf-input::placeholder,.gf-textarea::placeholder{color:#bdc1c6}

/* Secret msg */
#secret-msg{font-size:12px;color:var(--pul);font-style:italic;opacity:0;margin-top:6px;transition:opacity 1.4s ease;pointer-events:none}
#secret-msg.show{opacity:1}

/* Final button */
.gf-ok-btn{
  margin-top:16px;padding:10px 36px;background:var(--pu);color:#fff;
  border:none;border-radius:4px;font-size:14px;font-weight:500;
  font-family:'Roboto',sans-serif;cursor:pointer;transition:background .2s,box-shadow .2s;letter-spacing:.5px;
}
.gf-ok-btn:hover{background:#5e35b1;box-shadow:0 1px 3px rgba(0,0,0,.3)}
.gf-ok-btn.done{background:#c8e6c9;color:#2e7d32;cursor:default;pointer-events:none}

/* Progress */
#progress-bar-wrap{position:fixed;bottom:0;left:0;right:0;height:4px;background:#e0e0e0;z-index:200}
#progress-bar{height:100%;background:var(--pu);width:0%;transition:width .4s ease}

/* Submit row */
.gf-submit-row{display:flex;align-items:center;gap:20px;padding:8px 0 20px}
.gf-submit-btn{
  padding:10px 24px;background:var(--pu);color:#fff;border:none;border-radius:4px;
  font-size:14px;font-weight:500;font-family:'Roboto',sans-serif;
  cursor:pointer;transition:background .2s,box-shadow .2s;letter-spacing:.5px;
}
.gf-submit-btn:hover{background:#5e35b1;box-shadow:0 1px 3px rgba(0,0,0,.3)}
.gf-clear-link{font-size:14px;color:var(--blue);cursor:pointer}
.gf-clear-link:hover{text-decoration:underline}
.gf-footer{font-size:13px;color:var(--sub);padding-bottom:40px;line-height:1.7}
.gf-footer a{color:var(--blue)}

/* Heart float */
.heart-float{position:fixed;pointer-events:none;z-index:600;animation:floatUp 3.5s ease forwards;opacity:0}
@keyframes floatUp{
  0%{opacity:0;transform:translateY(0) scale(.5)}
  20%{opacity:1;transform:translateY(-30px) scale(1)}
  80%{opacity:.7;transform:translateY(-120px) scale(.8)}
  100%{opacity:0;transform:translateY(-180px) scale(.3)}
}
.shatter-piece{position:fixed;z-index:500;pointer-events:none;transform-origin:center;will-change:transform,opacity}

/* ── PHASE 2 ── */
#phase2{display:none;position:fixed;inset:0;z-index:1000;overflow:hidden;background:#080010}
#three-canvas{position:absolute;inset:0;z-index:0}
#mouse-glow{
  position:absolute;width:320px;height:320px;border-radius:50%;
  background:radial-gradient(circle,rgba(255,80,120,.16) 0%,rgba(180,0,80,.06) 50%,transparent 70%);
  pointer-events:none;z-index:1;transform:translate(-50%,-50%);
  left:50%;top:50%;
}

#confession-card{
  position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  z-index:5;width:min(580px,94vw);max-height:90vh;overflow-y:auto;
  background:rgba(255,255,255,.07);
  backdrop-filter:blur(22px) saturate(160%);-webkit-backdrop-filter:blur(22px) saturate(160%);
  border:1px solid rgba(255,255,255,.14);border-radius:24px;
  padding:40px 36px 44px;
  box-shadow:0 8px 64px rgba(255,60,100,.18),0 0 0 1px rgba(255,255,255,.07) inset;
  opacity:0;scrollbar-width:none;
}
#confession-card::-webkit-scrollbar{display:none}

.card-title{
  font-family:'Dancing Script',cursive;font-size:clamp(24px,4.5vw,36px);font-weight:700;
  text-align:center;
  background:linear-gradient(135deg,#ffb3d0,#ff4d88,#cc66ff,#ff4d88);
  background-size:200% 200%;
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:gradShift 3s ease infinite;
  filter:drop-shadow(0 0 16px rgba(255,80,140,.5));
  line-height:1.3;margin-bottom:6px;
}
@keyframes gradShift{0%,100%{background-position:0 50%}50%{background-position:100% 50%}}
.card-sub{font-size:12px;color:rgba(255,200,220,.5);text-align:center;letter-spacing:2.5px;text-transform:uppercase;margin-bottom:28px;font-family:'Roboto',sans-serif}
.card-div{height:1px;background:linear-gradient(90deg,transparent,rgba(255,100,160,.35),transparent);margin:16px 0}

/* Message lines — opacity-based animation, always white/pink, no color interpolation */
.msg-line{
  font-size:15px;line-height:1.9;margin-bottom:14px;
  font-family:'Noto Sans SC','Roboto',sans-serif;font-weight:300;
  color:rgba(255,225,235,.92);
  opacity:0;
  transform:translateY(10px);
}
.msg-final{
  font-size:15.5px;line-height:2;margin-top:18px;
  font-family:'Noto Sans SC','Roboto',sans-serif;font-weight:400;
  text-align:center;padding:20px 16px;
  border:1px solid rgba(255,120,160,0);border-radius:12px;
  background:rgba(255,80,120,0);
  color:rgba(255,215,230,.96);
  white-space:pre-line;
  opacity:0;
  transform:translateY(12px);
}
</style>
</head>
<body>

<!-- ══════════════ PHASE 1 ══════════════ -->
<div id="phase1">

  <div class="gf-topbar">
    <div class="gf-logo">
      <span style="color:#4285f4">G</span><span style="color:#ea4335">o</span><span style="color:#fbbc05">o</span><span style="color:#34a853">g</span><span style="color:#4285f4">l</span><span style="color:#ea4335">e</span>&nbsp;<span style="color:var(--pu)">Forms</span>
    </div>
  </div>

  <div id="easter-avatar">A</div>

  <div class="gf-wrap">

    <div class="gf-title-card">
      <div class="gf-form-title">【BU COM 学术调研】波士顿地区大学生社交媒体依赖与亲密关系连结研究</div>
      <div class="gf-form-desc">Researcher: Aving. 本问卷旨在探究波士顿地区（如查尔斯河畔、Newbury等活动区域）年轻人的数字媒介使用习惯。预计用时 3 分钟，所有数据仅作学术统计。</div>
      <div class="gf-req-note"><em>*</em> 表示必填问题</div>
    </div>

    <!-- Q1 Likert -->
    <div class="gf-card" id="card-q1">
      <div class="gf-qlabel">1. 你多常通过线上消息（而非线下见面）来获得情感支持？<span class="req">*</span></div>
      <div class="gf-likert">
        <div class="gf-lside l">Never/<br>Nope</div>
        <div class="gf-lopts">
          <div class="gf-lcol" onclick="selLikert('q1',1)"><div class="gf-lnum">1</div><div class="gf-radio" id="q1-r1"></div></div>
          <div class="gf-lcol" onclick="selLikert('q1',2)"><div class="gf-lnum">2</div><div class="gf-radio" id="q1-r2"></div></div>
          <div class="gf-lcol" onclick="selLikert('q1',3)"><div class="gf-lnum">3</div><div class="gf-radio" id="q1-r3"></div></div>
          <div class="gf-lcol" onclick="selLikert('q1',4)"><div class="gf-lnum">4</div><div class="gf-radio" id="q1-r4"></div></div>
          <div class="gf-lcol" onclick="selLikert('q1',5)"><div class="gf-lnum">5</div><div class="gf-radio" id="q1-r5"></div></div>
        </div>
        <div class="gf-lside r">Always</div>
      </div>
    </div>

    <!-- Q2 Text -->
    <div class="gf-card" id="card-q2">
      <div class="gf-qlabel">2. 在波士顿，你最常去哪个区域放松或寻找灵感？（如 Beacon Hill, Seaport 等）<span class="req">*</span></div>
      <div class="gf-input-wrap">
        <input class="gf-input" id="q2-input" type="text" placeholder="填写你的回答" autocomplete="off">
      </div>
    </div>

    <!-- Q3 Radio -->
    <div class="gf-card" id="card-q3">
      <div class="gf-qlabel">3. 你通常更倾向于通过哪种方式表达关心？<span class="req">*</span></div>
      <div class="gf-radio-group" id="q3-opts">
        <div class="gf-radio-item" onclick="selRadio('q3',this)"><div class="gf-dot" id="q3-r0"></div><span>发消息或语音</span></div>
        <div class="gf-radio-item" onclick="selRadio('q3',this)"><div class="gf-dot" id="q3-r1"></div><span>亲自陪伴或见面</span></div>
        <div class="gf-radio-item" onclick="selRadio('q3',this)"><div class="gf-dot" id="q3-r2"></div><span>送礼物或写信</span></div>
        <div class="gf-radio-item" onclick="selRadio('q3',this)"><div class="gf-dot" id="q3-r3"></div><span>帮对方做一些具体的事</span></div>
      </div>
    </div>

    <!-- Q4 Likert -->
    <div class="gf-card" id="card-q4">
      <div class="gf-qlabel">4. 当你感到疲惫时，数字社交是否会让你感觉更消耗？<span class="req">*</span></div>
      <div class="gf-likert">
        <div class="gf-lside l">完全<br>不会</div>
        <div class="gf-lopts">
          <div class="gf-lcol" onclick="selLikert('q4',1)"><div class="gf-lnum">1</div><div class="gf-radio" id="q4-r1"></div></div>
          <div class="gf-lcol" onclick="selLikert('q4',2)"><div class="gf-lnum">2</div><div class="gf-radio" id="q4-r2"></div></div>
          <div class="gf-lcol" onclick="selLikert('q4',3)"><div class="gf-lnum">3</div><div class="gf-radio" id="q4-r3"></div></div>
          <div class="gf-lcol" onclick="selLikert('q4',4)"><div class="gf-lnum">4</div><div class="gf-radio" id="q4-r4"></div></div>
          <div class="gf-lcol" onclick="selLikert('q4',5)"><div class="gf-lnum">5</div><div class="gf-radio" id="q4-r5"></div></div>
        </div>
        <div class="gf-lside r">非常会/<br>Always</div>
      </div>
    </div>

    <!-- Q5 Textarea -->
    <div class="gf-card" id="card-q5">
      <div class="gf-qlabel">5. 请描述一次让你感受到"真实连结"的线下互动经历。（可以是任何人）<span class="req">*</span></div>
      <div class="gf-input-wrap">
        <textarea class="gf-textarea" id="q5-input" rows="3" placeholder="填写你的回答"></textarea>
      </div>
    </div>

    <!-- Q6 Checkbox -->
    <div class="gf-card" id="card-q6">
      <div class="gf-qlabel">6. 以下哪些因素会让你在线下关系中感到安全感？（可多选）<span class="req">*</span></div>
      <div class="gf-checkbox-group" id="q6-opts">
        <div class="gf-check-item" onclick="toggleCheck('q6',this)"><div class="gf-checkmark" id="q6-c0"></div><span>对方的陪伴与稳定</span></div>
        <div class="gf-check-item" onclick="toggleCheck('q6',this)"><div class="gf-checkmark" id="q6-c1"></div><span>彼此坦诚地表达情绪</span></div>
        <div class="gf-check-item" onclick="toggleCheck('q6',this)"><div class="gf-checkmark" id="q6-c2"></div><span>共同经历某件事</span></div>
        <div class="gf-check-item" onclick="toggleCheck('q6',this)"><div class="gf-checkmark" id="q6-c3"></div><span>被对方记住小细节</span></div>
        <div class="gf-check-item" onclick="toggleCheck('q6',this)"><div class="gf-checkmark" id="q6-c4"></div><span>不需要解释就被理解</span></div>
      </div>
    </div>

    <!-- Q7 Likert -->
    <div class="gf-card" id="card-q7">
      <div class="gf-qlabel">7. 你觉得自己目前的线下亲密关系，有多令你满意？<span class="req">*</span></div>
      <div class="gf-likert">
        <div class="gf-lside l">完全<br>不满意</div>
        <div class="gf-lopts">
          <div class="gf-lcol" onclick="selLikert('q7',1)"><div class="gf-lnum">1</div><div class="gf-radio" id="q7-r1"></div></div>
          <div class="gf-lcol" onclick="selLikert('q7',2)"><div class="gf-lnum">2</div><div class="gf-radio" id="q7-r2"></div></div>
          <div class="gf-lcol" onclick="selLikert('q7',3)"><div class="gf-lnum">3</div><div class="gf-radio" id="q7-r3"></div></div>
          <div class="gf-lcol" onclick="selLikert('q7',4)"><div class="gf-lnum">4</div><div class="gf-radio" id="q7-r4"></div></div>
          <div class="gf-lcol" onclick="selLikert('q7',5)"><div class="gf-lnum">5</div><div class="gf-radio" id="q7-r5"></div></div>
        </div>
        <div class="gf-lside r">非常<br>满意</div>
      </div>
    </div>

    <!-- Q8 Radio -->
    <div class="gf-card" id="card-q8">
      <div class="gf-qlabel">8. 如果你和某人关系很好，你更希望对方如何表达对你的珍惜？<span class="req">*</span></div>
      <div class="gf-radio-group" id="q8-opts">
        <div class="gf-radio-item" onclick="selRadio('q8',this)"><div class="gf-dot" id="q8-r0"></div><span>说出来，直接告诉我</span></div>
        <div class="gf-radio-item" onclick="selRadio('q8',this)"><div class="gf-dot" id="q8-r1"></div><span>用行动，比如陪伴和帮助</span></div>
        <div class="gf-radio-item" onclick="selRadio('q8',this)"><div class="gf-dot" id="q8-r2"></div><span>记住我提到的每一个细节</span></div>
        <div class="gf-radio-item" onclick="selRadio('q8',this)"><div class="gf-dot" id="q8-r3"></div><span>给我一点私人空间，但始终在线</span></div>
      </div>
    </div>

    <!-- Q9 Text -->
    <div class="gf-card" id="card-q9">
      <div class="gf-qlabel">9. 用一个词，形容你心目中"理想陪伴"的感觉。<span class="req">*</span></div>
      <div class="gf-input-wrap">
        <input class="gf-input" id="q9-input" type="text" placeholder="填写你的回答" autocomplete="off">
      </div>
    </div>

    <!-- Q10 FINAL — only ONE button -->
    <div class="gf-card" id="card-q10">
      <div class="gf-qlabel">10. 总体而言，你是否愿意在未来投入更多时间来维护真实、深度的线下亲密关系？<span class="req">*</span></div>
      <div id="secret-msg">*Say YES to being my forever babe.*</div>
      <div style="margin-top:14px">
        <button class="gf-ok-btn" id="q10-btn" onclick="answerFinal()">好</button>
      </div>
    </div>

    <div class="gf-submit-row">
      <button class="gf-submit-btn" onclick="handleSubmit()">提交</button>
      <span class="gf-clear-link" onclick="clearForm()">清除表单</span>
    </div>
    <div class="gf-footer">
      切勿通过 Google 表单提交密码。<br>
      <a href="#">报告滥用行为</a> · <a href="#">服务条款</a> · <a href="#">隐私权政策</a>
    </div>
  </div>

  <div id="progress-bar-wrap"><div id="progress-bar"></div></div>
</div>

<!-- ══════════════ PHASE 2 ══════════════ -->
<div id="phase2">
  <canvas id="three-canvas"></canvas>
  <div id="mouse-glow"></div>
  <div id="confession-card">
    <div class="card-title">Happy 19th Birthday, Cynthia! ❤️</div>
    <div class="card-sub">A message just for you · from Gavin</div>
    <div class="card-div"></div>
    <div id="p2-m1" class="msg-line"></div>
    <div id="p2-m2" class="msg-line"></div>
    <div id="p2-m3" class="msg-line"></div>
    <div id="p2-m4" class="msg-line"></div>
    <div class="card-div"></div>
    <div id="p2-final" class="msg-final"></div>
  </div>
</div>

<script>
// ── State ──
const A={q1:0,q2:'',q3:'',q4:0,q5:'',q6:[],q7:0,q8:'',q9:'',q10:false};
let easterDone=false,submitted=false;

// ── Progress ──
function countFilled(){
  return [A.q1>0,A.q2.trim(),A.q3,A.q4>0,A.q5.trim(),A.q6.length>0,A.q7>0,A.q8,A.q9.trim(),A.q10]
    .filter(Boolean).length;
}
function updateProgress(){
  document.getElementById('progress-bar').style.width=(countFilled()/10*100)+'%';
}

// ── Likert ──
function selLikert(q,v){
  A[q]=v;
  for(let i=1;i<=5;i++){
    const el=document.getElementById(q+'-r'+i);
    if(el) el.classList.toggle('sel',i===v);
  }
  updateProgress();
}

// ── Radio (single) — uses .gf-dot inside .gf-radio-item ──
function selRadio(q,clickedItem){
  A[q]=clickedItem.querySelector('span').textContent;
  const opts=document.getElementById(q+'-opts');
  opts.querySelectorAll('.gf-dot').forEach(d=>d.classList.remove('sel'));
  clickedItem.querySelector('.gf-dot').classList.add('sel');
  updateProgress();
}

// ── Checkbox ──
function toggleCheck(q,clickedItem){
  const val=clickedItem.querySelector('span').textContent;
  const idx=A[q].indexOf(val);
  if(idx===-1){A[q].push(val);}else{A[q].splice(idx,1);}
  clickedItem.querySelector('.gf-checkmark').classList.toggle('sel',A[q].includes(val));
  updateProgress();
}

// ── Text inputs ──
document.getElementById('q2-input').addEventListener('input',function(){A.q2=this.value;updateProgress()});
document.getElementById('q5-input').addEventListener('input',function(){A.q5=this.value;updateProgress()});
document.getElementById('q9-input').addEventListener('input',function(){A.q9=this.value;updateProgress()});

// ── Final Q10 ──
function answerFinal(){
  A.q10=true;
  const btn=document.getElementById('q10-btn');
  btn.textContent='✓ 好的！';
  btn.classList.add('done');
  updateProgress();
  const rect=btn.getBoundingClientRect();
  ['❤️','💕','🌸','💖','✨'].forEach((h,i)=>{
    const el=document.createElement('div');
    el.className='heart-float';
    el.textContent=h;
    el.style.cssText='left:'+(rect.left+rect.width/2+(Math.random()-.5)*80)+'px;top:'+rect.top+'px;font-size:'+(16+Math.random()*10)+'px;animation-delay:'+(i*.12)+'s';
    document.body.appendChild(el);
    setTimeout(()=>el.remove(),4000);
  });
}

// ── Easter egg ──
document.getElementById('easter-avatar').addEventListener('click',function(){
  if(!easterDone){
    easterDone=true;
    document.getElementById('secret-msg').classList.add('show');
    this.style.color='rgba(103,58,183,.55)';
  }
});

// ── Clear ──
function clearForm(){
  Object.assign(A,{q1:0,q2:'',q3:'',q4:0,q5:'',q6:[],q7:0,q8:'',q9:'',q10:false});
  ['q1','q4','q7'].forEach(q=>{for(let i=1;i<=5;i++){const el=document.getElementById(q+'-r'+i);if(el)el.classList.remove('sel')}});
  ['q3','q8'].forEach(q=>{const opts=document.getElementById(q+'-opts');if(opts)opts.querySelectorAll('.gf-dot').forEach(d=>d.classList.remove('sel'))});
  const q6opts=document.getElementById('q6-opts');
  if(q6opts)q6opts.querySelectorAll('.gf-checkmark').forEach(c=>c.classList.remove('sel'));
  ['q2-input','q5-input','q9-input'].forEach(id=>{document.getElementById(id).value=''});
  const btn=document.getElementById('q10-btn');
  btn.textContent='好';btn.classList.remove('done');
  document.getElementById('secret-msg').classList.remove('show');
  updateProgress();
}

// ── Submit ──
function handleSubmit(){
  if(submitted) return;
  const missing=[];
  if(!A.q1) missing.push('q1');
  if(!A.q2.trim()) missing.push('q2');
  if(!A.q3) missing.push('q3');
  if(!A.q4) missing.push('q4');
  if(!A.q5.trim()) missing.push('q5');
  if(!A.q6.length) missing.push('q6');
  if(!A.q7) missing.push('q7');
  if(!A.q8) missing.push('q8');
  if(!A.q9.trim()) missing.push('q9');
  if(!A.q10) missing.push('q10');
  if(missing.length){shakeCards(missing);return;}
  submitted=true;
  doShatter();
}
function shakeCards(qs){
  qs.forEach(q=>{
    const c=document.getElementById('card-'+q);
    if(!c)return;
    c.style.border='1.5px solid #d93025';
    gsap.to(c,{x:-5,duration:.07,repeat:5,yoyo:true,ease:'power1.inOut',
      onComplete:()=>{c.style.border='';gsap.set(c,{x:0})}});
  });
}

// ── Shatter transition ──
function doShatter(){
  const p1=document.getElementById('phase1');
  const pieces=[];
  for(let i=0;i<22;i++){
    const d=document.createElement('div');
    d.className='shatter-piece';
    const w=60+Math.random()*200,h=50+Math.random()*140;
    d.style.cssText='width:'+w+'px;height:'+h+'px;left:'+Math.random()*window.innerWidth+'px;top:'+Math.random()*window.innerHeight+'px;background:rgba(255,255,255,'+(0.45+Math.random()*.55)+');border-radius:'+(Math.random()*6)+'px';
    document.body.appendChild(d);pieces.push(d);
  }
  const tl=gsap.timeline({onComplete:startP2});
  tl.to(p1,{opacity:0,scale:1.03,duration:.45,ease:'power2.in'},0);
  pieces.forEach((p,i)=>{
    tl.to(p,{
      x:(Math.random()-.5)*1000,y:(Math.random()-.5)*800-200,
      rotation:(Math.random()-.5)*900,opacity:0,scale:.1,
      duration:.7+Math.random()*.45,ease:'power3.out'
    },0.06+i*.016);
  });
  tl.add(()=>pieces.forEach(p=>p.remove()),1.2);
}

// ── Phase 2 ──
function startP2(){
  const p2=document.getElementById('phase2');
  p2.style.display='block';
  initThree();
  buildMsgs();
  revealCard();
  heartRain();
}

// ── Build messages ──
function buildMsgs(){
  const loc=A.q2.trim()||'波士顿';

  let m1='';
  if(A.q1>=4) m1='你说你常依赖线上，但你知道吗，I luv u，无论线上线下，我的心永远在线等你。';
  else if(A.q1===3) m1='是不是填问卷觉得有点无聊啦？宝宝想睡觉了吗？困嘛？靠在我肩膀上吧。';
  else m1='你说你不需要线上支持，那你会推开我吗？绝对不会 — 我会一直在你身边。';

  const m2='原来你喜欢去 '+loc+'，那我们下次就牵着手去那里，创造只属于我们19岁的回忆。';

  let m3='';
  if(A.q4>=4) m3='如果世界让你疲惫，那就躲进我的怀里，做个无需社交的小孩。';
  else m3='只要有你在，波士顿的冬天都不再难熬。';

  const word=A.q9.trim()||'温柔';
  const m4='你用"'+word+'"来形容理想的陪伴 — 那我会用一辈子去学着成为那个答案。';

  const mFinal='既然你点了"好"，那这辈子你都逃不掉了。\n\n19岁生日快乐，Cynthia。\n\n永远爱你的 Gavin。❤️';

  document.getElementById('p2-m1').textContent=m1;
  document.getElementById('p2-m2').textContent=m2;
  document.getElementById('p2-m3').textContent=m3;
  document.getElementById('p2-m4').textContent=m4;
  document.getElementById('p2-final').textContent=mFinal;
}

// ── Reveal — pure opacity + translateY, no color animation ──
function revealCard(){
  gsap.to('#confession-card',{opacity:1,duration:1.2,ease:'power2.out',delay:.3});

  ['#p2-m1','#p2-m2','#p2-m3','#p2-m4'].forEach((sel,i)=>{
    gsap.to(sel,{
      opacity:1,
      y:0,
      duration:.95,
      delay:1.3+i*1.5,
      ease:'power2.out'
    });
  });

  // Final: opacity + CSS transition for border/bg
  gsap.to('#p2-final',{
    opacity:1,y:0,duration:1.3,delay:8.0,ease:'power2.out',
    onStart:()=>{
      setTimeout(()=>{
        const el=document.getElementById('p2-final');
        el.style.transition='border-color 1.3s ease, background 1.3s ease';
        el.style.borderColor='rgba(255,120,160,.28)';
        el.style.background='rgba(255,80,120,.07)';
      },50);
    }
  });
}

// ── Three.js starfield ──
function initThree(){
  const canvas=document.getElementById('three-canvas');
  const renderer=new THREE.WebGLRenderer({canvas,antialias:true,alpha:true});
  renderer.setSize(window.innerWidth,window.innerHeight);
  renderer.setPixelRatio(Math.min(devicePixelRatio,2));

  const scene=new THREE.Scene();
  const camera=new THREE.PerspectiveCamera(75,window.innerWidth/window.innerHeight,.1,1000);
  camera.position.z=5;

  const sGeo=new THREE.BufferGeometry();
  const sN=2400,sPos=new Float32Array(sN*3),sCol=new Float32Array(sN*3);
  for(let i=0;i<sN;i++){
    sPos[i*3]=(Math.random()-.5)*46;sPos[i*3+1]=(Math.random()-.5)*46;sPos[i*3+2]=(Math.random()-.5)*46;
    sCol[i*3]=.88+Math.random()*.12;sCol[i*3+1]=.65+Math.random()*.35;sCol[i*3+2]=.78+Math.random()*.22;
  }
  sGeo.setAttribute('position',new THREE.BufferAttribute(sPos,3));
  sGeo.setAttribute('color',new THREE.BufferAttribute(sCol,3));
  const sMat=new THREE.PointsMaterial({size:.055,vertexColors:true,transparent:true,opacity:.88});
  const stars=new THREE.Points(sGeo,sMat);scene.add(stars);

  const pGeo=new THREE.BufferGeometry();
  const pN=280,pPos=new Float32Array(pN*3),pVel=[];
  for(let i=0;i<pN;i++){
    pPos[i*3]=(Math.random()-.5)*22;pPos[i*3+1]=(Math.random()-.5)*22;pPos[i*3+2]=(Math.random()-.5)*10;
    pVel.push({x:(Math.random()-.5)*.003,y:(Math.random()-.5)*.003+.0008});
  }
  pGeo.setAttribute('position',new THREE.BufferAttribute(pPos,3));
  const pMat=new THREE.PointsMaterial({size:.1,color:0xff5588,transparent:true,opacity:.42});
  const ptcls=new THREE.Points(pGeo,pMat);scene.add(ptcls);

  let mx=0,my=0;
  const glow=document.getElementById('mouse-glow');
  document.addEventListener('mousemove',e=>{
    mx=(e.clientX/window.innerWidth-.5)*2;my=-(e.clientY/window.innerHeight-.5)*2;
    glow.style.left=e.clientX+'px';glow.style.top=e.clientY+'px';
  });
  window.addEventListener('resize',()=>{
    camera.aspect=window.innerWidth/window.innerHeight;camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth,window.innerHeight);
  });

  let t=0;
  (function loop(){
    requestAnimationFrame(loop);t+=.003;
    stars.rotation.y=t*.07+mx*.025;stars.rotation.x=t*.035+my*.025;
    ptcls.rotation.y=-t*.04;
    const pp=pGeo.attributes.position.array;
    for(let i=0;i<pN;i++){
      pp[i*3]+=pVel[i].x;pp[i*3+1]+=pVel[i].y;
      if(pp[i*3+1]>12)pp[i*3+1]=-12;
    }
    pGeo.attributes.position.needsUpdate=true;
    renderer.render(scene,camera);
  })();
}

// ── Heart rain ──
function heartRain(){
  const hs=['❤️','💕','💖','🌸','✨','💗','🫶'];
  const p2=document.getElementById('phase2');
  function drop(){
    if(p2.style.display==='none')return;
    const el=document.createElement('div');
    el.style.cssText='position:fixed;top:-28px;left:'+(Math.random()*100)+'vw;font-size:'+(13+Math.random()*10)+'px;pointer-events:none;z-index:4;opacity:0';
    el.textContent=hs[Math.floor(Math.random()*hs.length)];
    p2.appendChild(el);
    gsap.to(el,{y:window.innerHeight+60,opacity:.6,duration:4.5+Math.random()*3,ease:'none',onComplete:()=>el.remove()});
    gsap.to(el,{opacity:0,duration:.8,delay:3.5+Math.random()*2});
    setTimeout(drop,500+Math.random()*900);
  }
  setTimeout(drop,900);
}
</script>
</body>
</html>
