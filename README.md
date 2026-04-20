<!DOCTYPE html>
<html lang="en-PH">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SkibiVote — * It's a VOTING experience.</title>
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&family=Courier+Prime:wght@400;700&display=swap" rel="stylesheet">
<style>
*{cursor:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 16 16'%3E%3Cpath fill='%23ffffff' d='M8 14s-6-4.5-6-8a4 4 0 0 1 6-3.46A4 4 0 0 1 14 6c0 3.5-6 8-6 8z'/%3E%3C/svg%3E") 8 14, auto !important;}
button,a,[onclick]{cursor:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' viewBox='0 0 16 16'%3E%3Cpath fill='%23ffff00' d='M8 14s-6-4.5-6-8a4 4 0 0 1 6-3.46A4 4 0 0 1 14 6c0 3.5-6 8-6 8z'/%3E%3C/svg%3E") 8 14, pointer !important;}
</style>
<style>
:root{
  --black:#000000;--ink:#0a0a0a;--dark:#111111;--mid:#1a1a1a;--rule:#333;--muted:#888;--subtle:#666;--silver:#aaa;--off:#e0e0e0;--white:#ffffff;
  --ut-yellow:#ffff00;--ut-cyan:#00ffff;--ut-red:#ff0000;--ut-heart:#ff4444;--ut-green:#00ff00;--ut-blue:#6060ff;
  --font-main:'VT323',monospace;--font-pixel:'Press Start 2P',monospace;--font-mono:'Courier Prime',monospace;
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;border-radius:0!important;}
html,body{height:100%;font-family:var(--font-main);background:var(--black);color:var(--white);font-size:20px;image-rendering:pixelated;overflow:hidden;}
button{cursor:pointer;font-family:var(--font-main);}
body::after{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.15) 2px,rgba(0,0,0,.15) 4px);pointer-events:none;z-index:9999;}

.px,.topbar-title,.sh-title,.sc-label,.sb-ln,.sb-sec,.sb-badge,.vcpos,.vetitle,.vcounter,.possb-hd,.posit-check,.cnum,.posnav-info,.vsubmit,.ll-name,.lh,.ltab,.llabel,.lsucc-title,.lprogwrap,.profile-name,.pstat-val,.vhist-date,.cert-btn,.settings-section-title,.cat-name,.preview-title,.form-label,.poll-preview .preview-title,.mtitle,.page-header h2,.profile-badge.verified,.bvotes,.pill,.section-divider-label,.res-pos-name,.res-winner-label,.res-stat-label{font-family:'Press Start 2P',monospace!important;font-size:9px!important;letter-spacing:.3px!important;line-height:1.9!important;}
.topbar-title,.vcpos,.page-header h2,.ll-name{font-size:11px!important;}
.mtitle,.profile-name,.lh,.lsucc-title{font-size:11px!important;}
.sc-val,.pstat-val{font-size:15px!important;}
.ll-h1{font-family:'Press Start 2P',monospace!important;font-size:14px!important;line-height:2.1!important;}
.sb-ln{font-size:11px!important;}
.vcpos{font-size:13px!important;}
.res-pos-name{font-size:10px!important;}
.res-winner-label{font-size:8px!important;color:var(--ut-yellow)!important;}
.res-stat-label{font-size:8px!important;color:var(--muted)!important;}

body,.sb-un,.sb-ur,.sb-logout,.sb-it,.sc-sub,.btitle,.bdesc,.btime,.cname,.cparty,.linput,.sinput,.form-input,.cand-inp,.pos-title-inp,.settings-row-label,.settings-row-sub,.vhist-title,.vhist-sub,.profile-id,.lsub,.ll-p,.ll-sl,.msub,.mpos,.mcand,.cert-box,.preview-pos,.preview-cands,.cat-count,.cat-desc,.chip,.lerr,.ldivt,.ldemo *,.posnav-btn,.vback,.btn,.lbtn,.mcancel,.mconfirm,.empty-state,.empty-state a,.bdesc,.cand-vote-label,.cand-vote-pct,.cand-vote-bar-wrap,.res-cand-name,.res-cand-party,.res-total-label,.pos-preset-item{font-family:'VT323',monospace!important;font-size:20px!important;}
.btitle{font-size:20px!important;}.cname{font-size:23px!important;}.lbtn,.mconfirm{font-size:22px!important;}.btn{font-size:19px!important;}.sb-it{font-size:19px!important;}.settings-row-label{font-size:20px!important;}.settings-row-sub{font-size:17px!important;}.vhist-title{font-size:19px!important;}.vhist-sub{font-size:17px!important;}.bdesc{font-size:17px!important;}.ll-p{font-size:19px!important;}.lsub{font-size:19px!important;}.msub{font-size:19px!important;}.cat-desc{font-size:17px!important;}.cparty{font-size:17px!important;}
.res-cand-name{font-size:21px!important;}.res-cand-party{font-size:16px!important;}.res-total-label{font-size:17px!important;color:var(--muted)!important;}
.pos-preset-item{font-size:18px!important;}

.topbar-title,.vcpos,.sc-val,.pstat-val,.ll-name,.ll-h1 em,.profile-name,.page-header h2,.mtitle,.posit-check,.sh-title::before,.section-divider-label{color:var(--ut-yellow)!important;}
.sc-val,.pstat-val,.sb-ur,.profile-id{color:var(--ut-cyan)!important;}
.sb-it,.btitle,.cname,.settings-row-label,.vhist-title,.cat-name,.lh,.ll-h1,.vetitle,.posit-name{color:#fff!important;}

.sb{border-right:3px solid #fff!important;background:#000!important;}.sb-logo{border-bottom:3px solid #fff!important;}.sb-user{border-bottom:3px solid #fff!important;}.sb-foot{border-top:3px solid #fff!important;}.topbar{border-bottom:3px solid #fff!important;}.ll{border-right:3px solid #fff!important;}.ll-bottom .ll-stats{border-top:3px solid #fff!important;}.vhdr{border-bottom:3px solid #fff!important;}.possb{border-right:3px solid #fff!important;}

.sc,.bi,.ccard,.vhist-item,.profile-hero,.pstat,.cat-card,.pos-builder,.poll-preview,.settings-row,.mbox,.cert-box,.mrow{border:3px solid #333!important;background:#000!important;}
.bi:hover,.sc:hover,.ccard:hover,.vhist-item:hover,.settings-row:hover,.cat-card:hover{border-color:var(--ut-yellow)!important;box-shadow:0 0 10px rgba(255,255,0,.25)!important;}
.ccard.sel{border-color:var(--ut-yellow)!important;box-shadow:0 0 16px rgba(255,255,0,.4)!important;}
.cat-card.followed{border-color:var(--ut-yellow)!important;}
.mbox{border:4px solid #fff!important;box-shadow:6px 6px 0 #fff!important;}
.profile-hero{border:3px solid #fff!important;}.pstat{border:3px solid #fff!important;}.poll-preview{border:3px solid #fff!important;box-shadow:4px 4px 0 #fff!important;}

.lbtn,.btn-white,.mconfirm{background:#fff!important;color:#000!important;border:3px solid #fff!important;}
.lbtn:hover,.btn-white:hover,.mconfirm:hover{background:var(--ut-yellow)!important;border-color:var(--ut-yellow)!important;box-shadow:0 0 14px rgba(255,255,0,.5)!important;}
.lbtn.ghost,.btn-ghost,.mcancel,.vback,.posnav-btn{background:#000!important;color:#aaa!important;border:3px solid #444!important;}
.lbtn.ghost:hover,.btn-ghost:hover,.mcancel:hover,.vback:hover,.posnav-btn:hover{border-color:#fff!important;color:#fff!important;}
.posnav-btn.pri{background:#fff!important;color:#000!important;border-color:#fff!important;}.posnav-btn.pri:hover{background:var(--ut-yellow)!important;border-color:var(--ut-yellow)!important;}
.vsubmit{padding:9px 19px;background:#fff!important;color:#000!important;border:3px solid #fff!important;}.vsubmit.ready:hover{background:var(--ut-yellow)!important;border-color:var(--ut-yellow)!important;}
.fab{background:var(--ut-yellow)!important;color:#000!important;border:3px solid #fff!important;box-shadow:4px 4px 0 #fff!important;}.fab:hover{transform:translate(-2px,-2px)!important;box-shadow:6px 6px 0 #fff!important;}
.icobtn{border:3px solid #fff!important;background:#000!important;}.icobtn:hover{border-color:var(--ut-yellow)!important;}

input,select,textarea,.linput,.sinput,.form-input,.cand-inp,.s-input{border:3px solid #fff!important;background:#000!important;color:#fff!important;font-family:'VT323',monospace!important;font-size:20px!important;}
input:focus,select:focus,textarea:focus,.linput:focus,.sinput:focus,.form-input:focus{border-color:var(--ut-yellow)!important;box-shadow:0 0 8px rgba(255,255,0,.3)!important;}
.linput.err{border-color:var(--ut-red)!important;}

.ltabs,.ltab{border-color:#fff!important;}.ltab.active{background:#fff!important;color:#000!important;}.ltab{color:#666!important;background:#000!important;}
.chip{border:2px solid #333!important;color:#666!important;background:#000!important;font-size:16px!important;}.chip.active,.chip:hover{border-color:var(--ut-yellow)!important;color:var(--ut-yellow)!important;background:rgba(255,255,0,.06)!important;}
.p-live{border-color:var(--ut-yellow)!important;color:var(--ut-yellow)!important;}.p-upcoming{border-color:#555!important;color:#666!important;}.p-closed{border-color:#333!important;color:#444!important;}
.vbw{border:2px solid #fff!important;background:#1a1a1a!important;height:5px!important;}.vb{background:var(--ut-yellow)!important;}
.toggle{background:#333!important;border:2px solid #555!important;}.toggle.on{background:var(--ut-yellow)!important;border-color:var(--ut-yellow)!important;}.toggle::after{background:#666!important;}.toggle.on::after{background:#000!important;}
.toast{background:#000!important;border:4px solid var(--ut-yellow)!important;color:var(--ut-yellow)!important;box-shadow:4px 4px 0 var(--ut-yellow)!important;font-size:20px!important;}
.lprogwrap{border:2px solid #fff!important;background:#1a1a1a!important;height:8px!important;}.lprog{background:var(--ut-yellow)!important;}
.pwbar{height:3px!important;}
.sb-av{border:3px solid var(--ut-yellow)!important;color:var(--ut-cyan)!important;font-size:9px!important;}
.profile-avatar-big{border:3px solid var(--ut-yellow)!important;color:var(--ut-cyan)!important;box-shadow:0 0 14px rgba(255,255,0,.3)!important;}
.profile-badge.verified{border-color:var(--ut-yellow)!important;color:var(--ut-yellow)!important;}
::-webkit-scrollbar{width:6px!important;background:#000!important;}::-webkit-scrollbar-thumb{background:#fff!important;}
.sh-title::before{content:'* ';color:var(--ut-yellow);}
.sb-li{border:3px solid #fff!important;}.sb-ln{color:var(--ut-yellow)!important;text-shadow:2px 2px 0 rgba(255,255,0,.25)!important;}
.ll::before{background-image:linear-gradient(#222 1px,transparent 1px),linear-gradient(90deg,#222 1px,transparent 1px)!important;background-size:32px 32px!important;opacity:.6!important;}
.ccard.sel::after{content:'❤'!important;background:transparent!important;color:var(--ut-heart)!important;font-size:20px!important;animation:heartbeat .5s ease infinite!important;border:none!important;line-height:1!important;width:auto!important;height:auto!important;}
.posit.active{border-left:4px solid var(--ut-yellow)!important;background:rgba(255,255,0,.08)!important;}
.posit-check{color:var(--ut-yellow)!important;font-size:18px!important;font-family:'VT323',monospace!important;}
.add-cand-btn,.add-pos-btn{border:2px dashed #444!important;}.add-cand-btn:hover,.add-pos-btn:hover{border-color:var(--ut-yellow)!important;color:var(--ut-yellow)!important;}
.cert-btn{border:2px solid #333!important;font-size:11px!important;font-family:'Press Start 2P',monospace!important;}.cert-btn:hover{border-color:var(--ut-yellow)!important;color:var(--ut-yellow)!important;}
.empty-state a{color:var(--ut-yellow)!important;}
.ll-h1,.vcpos,.page-header h2,.mtitle,.profile-name,.lh{text-shadow:0 0 10px rgba(255,255,0,.3)!important;}

.section-divider{display:flex;align-items:center;gap:12px;margin:22px 0 14px;}
.section-divider-label{font-size:9px!important;}
.section-divider-line{flex:1;height:2px;background:var(--rule);}
.section-divider.polls-divider .section-divider-line{background:#444;}
.poll-tag{font-family:'Press Start 2P',monospace!important;font-size:7px!important;padding:2px 6px;border:2px solid var(--ut-cyan);color:var(--ut-cyan);margin-left:6px;vertical-align:middle;}
.election-tag{font-family:'Press Start 2P',monospace!important;font-size:7px!important;padding:2px 6px;border:2px solid var(--ut-yellow);color:var(--ut-yellow);margin-left:6px;vertical-align:middle;}

.cand-vote-stats{padding:6px 15px 13px;border-top:2px solid #222;}
.cand-vote-bar-wrap{width:100%;height:6px;background:#1a1a1a;border:2px solid #333;margin:4px 0;}
.cand-vote-bar{height:100%;background:var(--ut-yellow);transition:width .4s ease;}
.cand-vote-label{font-size:17px!important;color:#888;display:flex;justify-content:space-between;}
.cand-vote-pct{font-size:17px!important;color:var(--ut-yellow);}

#resultsPage{flex-direction:row;}
.res-header{display:flex;align-items:center;gap:13px;margin-bottom:22px;padding-bottom:18px;border-bottom:3px solid #fff;}
.res-back{display:flex;align-items:center;gap:6px;font-size:18px;color:var(--muted);cursor:pointer;padding:7px 13px;border:3px solid #444;background:#000;transition:all .15s;font-family:'VT323',monospace;}
.res-back:hover{color:#fff;border-color:#fff;}
.res-election-title{font-family:'Press Start 2P',monospace;font-size:12px;color:var(--ut-yellow);text-shadow:0 0 10px rgba(255,255,0,.3);}
.res-election-meta{font-size:17px;color:var(--muted);margin-top:4px;}
.res-stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:22px;}
.res-stat-card{background:#000;border:3px solid #333;padding:14px 16px;text-align:center;}
.res-stat-val{font-family:'Press Start 2P',monospace;font-size:15px;color:var(--ut-cyan);margin-bottom:6px;}
.res-pos-block{background:#000;border:3px solid #333;margin-bottom:16px;animation:fadeUp .4s ease both;}
.res-pos-block:hover{border-color:var(--ut-yellow);}
.res-pos-header{padding:14px 18px;border-bottom:3px solid #333;display:flex;align-items:center;justify-content:space-between;}
.res-cands{padding:14px 18px;display:flex;flex-direction:column;gap:10px;}
.res-cand-row{display:flex;align-items:center;gap:14px;padding:10px 14px;background:#000;border:2px solid #222;transition:border-color .15s;position:relative;}
.res-cand-row.winner{border-color:var(--ut-yellow);background:rgba(255,255,0,.04);}
.res-cand-row:hover{border-color:#555;}
.res-cand-rank{font-family:'Press Start 2P',monospace;font-size:9px;color:var(--muted);width:22px;flex-shrink:0;}
.res-cand-rank.gold{color:var(--ut-yellow);}
.res-cand-info{flex:1;min-width:0;}
.res-cand-bar-wrap{width:100%;height:8px;background:#1a1a1a;border:2px solid #333;margin-top:5px;overflow:hidden;}
.res-cand-bar{height:100%;transition:width .8s cubic-bezier(.4,0,.2,1);}
.res-cand-bar.first{background:var(--ut-yellow);}
.res-cand-bar.second{background:#aaa;}
.res-cand-bar.other{background:#444;}
.res-cand-votes{text-align:right;flex-shrink:0;}
.res-pct-badge{font-family:'Press Start 2P',monospace;font-size:9px;padding:3px 8px;border:2px solid;margin-bottom:4px;display:block;text-align:center;}
.res-pct-badge.first-b{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.res-pct-badge.other-b{border-color:#444;color:#666;}
.res-winner-crown{font-size:18px;position:absolute;top:-8px;right:10px;animation:heartbeat .8s ease infinite;}
.res-filter-tabs{display:flex;gap:6px;margin-bottom:18px;flex-wrap:wrap;}
.res-tab{padding:6px 14px;background:#000;border:2px solid #333;font-family:'VT323',monospace;font-size:18px;color:#666;cursor:pointer;transition:all .15s;}
.res-tab.active,.res-tab:hover{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.res-tab.active{background:rgba(255,255,0,.06);}
.res-turnout-bar{height:12px;background:#1a1a1a;border:2px solid #333;margin:8px 0;overflow:hidden;}
.res-turnout-fill{height:100%;background:var(--ut-yellow);transition:width 1s ease;}
.res-list-item{background:#000;border:3px solid #333;padding:14px 16px;display:flex;align-items:center;gap:13px;cursor:pointer;transition:all .2s;margin-bottom:6px;animation:fadeUp .4s ease both;}
.res-list-item:hover{border-color:var(--ut-yellow);}
.res-list-icon{width:38px;height:38px;border:2px solid #333;display:flex;align-items:center;justify-content:center;font-size:17px;flex-shrink:0;}
.res-list-status{font-family:'Press Start 2P',monospace;font-size:7px;padding:2px 6px;border:2px solid;}
.res-list-status.live{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.res-list-status.closed{border-color:#444;color:#666;}
.res-list-status.upcoming{border-color:#333;color:#555;}

.pos-preset-panel{background:#000;border:3px solid #333;margin-bottom:14px;overflow:hidden;}
.pos-preset-header{padding:10px 14px;border-bottom:2px solid #333;display:flex;align-items:center;justify-content:space-between;cursor:pointer;transition:border-color .15s;}
.pos-preset-header:hover{border-color:var(--ut-yellow);}
.pos-preset-title{font-family:'Press Start 2P',monospace;font-size:9px;color:var(--ut-yellow);}
.pos-preset-subtitle{font-size:16px;color:var(--muted);}
.pos-preset-body{display:none;padding:10px 14px 14px;}
.pos-preset-body.open{display:block;}
.pos-preset-group{margin-bottom:12px;}
.pos-preset-group-label{font-family:'Press Start 2P',monospace;font-size:8px;color:var(--muted);margin-bottom:6px;padding-bottom:4px;border-bottom:1px solid #222;}
.pos-preset-items{display:flex;flex-wrap:wrap;gap:6px;margin-top:6px;}
.pos-preset-item{padding:5px 11px;background:#000;border:2px solid #333;cursor:pointer;transition:all .15s;font-size:17px!important;}
.pos-preset-item:hover{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.pos-preset-item.used{border-color:#444;color:#555;cursor:not-allowed;}

@keyframes blink{0%,100%{opacity:1}49%{opacity:1}50%,99%{opacity:0}}
@keyframes fadeUp{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@keyframes spin{to{transform:rotate(360deg)}}
@keyframes popIn{from{opacity:0;transform:scale(.85)}to{opacity:1;transform:scale(1)}}
@keyframes heartbeat{0%,100%{transform:scale(1)}50%{transform:scale(1.2)}}
@keyframes glitch{0%,100%{text-shadow:2px 0 var(--ut-cyan),-2px 0 var(--ut-red)}33%{text-shadow:-2px 0 var(--ut-cyan),2px 0 var(--ut-red)}66%{text-shadow:0 0 transparent}}
@keyframes barGrow{from{width:0!important}to{}}
@keyframes slideIn{from{opacity:0;transform:translateX(20px)}to{opacity:1;transform:translateX(0)}}
@keyframes slideInLeft{from{opacity:0;transform:translateX(-20px)}to{opacity:1;transform:translateX(0)}}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}
@keyframes fabBounce{0%,100%{transform:translate(0,0)}50%{transform:translate(0,-4px)}}

.page{display:none;width:100vw;height:100vh;overflow:hidden;}
.page.active{display:flex;}

.sb{width:220px;background:var(--ink);border-right:1px solid var(--rule);display:flex;flex-direction:column;flex-shrink:0;height:100vh;}
.sb-logo{padding:20px 18px 16px;border-bottom:1px solid var(--rule);display:flex;align-items:center;gap:10px;}
.sb-li{width:34px;height:34px;border:1.5px solid var(--white);display:flex;align-items:center;justify-content:center;font-size:16px;}
.sb-ln{font-family:var(--font-pixel);font-weight:800;font-size:17px;letter-spacing:-.4px;}
.sb-user{padding:13px 16px;border-bottom:1px solid var(--rule);display:flex;align-items:center;gap:10px;}
.sb-av{width:36px;height:36px;background:var(--mid);border:1px solid var(--rule);border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:var(--font-pixel);font-weight:700;font-size:11px;flex-shrink:0;}
.sb-un{font-family:var(--font-main);font-weight:600;font-size:18px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.sb-ur{font-size:15px;color:var(--muted);margin-top:1px;}
.sb-nav{flex:1;padding:8px 0;overflow-y:auto;}
.sb-sec{font-size:9px;font-weight:600;letter-spacing:1.5px;text-transform:uppercase;color:var(--muted);padding:9px 16px 3px;font-family:var(--font-pixel);}
.sb-it{display:flex;align-items:center;gap:9px;padding:9px 16px;font-size:18px;color:var(--muted);cursor:pointer;transition:all .15s;border-left:2px solid transparent;user-select:none;}
.sb-it:hover{color:var(--white);background:rgba(255,255,255,.03);}
.sb-it.active{color:var(--white);border-left-color:var(--white);background:rgba(255,255,255,.05);}
.sb-badge{margin-left:auto;background:var(--white);color:var(--black);font-size:9px;font-weight:700;padding:1px 5px;border-radius:20px;}
.sb-foot{padding:13px 16px;border-top:1px solid var(--rule);}
.sb-logout{display:flex;align-items:center;gap:8px;font-size:18px;color:var(--muted);cursor:pointer;transition:color .15s;}
.sb-logout:hover{color:var(--white);}

.topbar{padding:14px 26px;border-bottom:1px solid var(--rule);display:flex;align-items:center;gap:13px;background:var(--black);flex-shrink:0;}
.topbar-title{font-family:var(--font-pixel);font-weight:700;font-size:15px;white-space:nowrap;}
.sw{flex:1;position:relative;max-width:440px;}
.sico{position:absolute;left:11px;top:50%;transform:translateY(-50%);font-size:14px;opacity:.4;pointer-events:none;}
.sinput{width:100%;background:var(--ink);border:1px solid var(--rule);padding:9px 12px 9px 34px;font-family:var(--font-main);font-size:18px;color:var(--white);outline:none;transition:border-color .2s;}
.sinput::placeholder{color:var(--muted);}.sinput:focus{border-color:var(--white);}
.tbr{margin-left:auto;display:flex;gap:8px;}
.icobtn{width:34px;height:34px;background:var(--ink);border:1px solid var(--rule);display:flex;align-items:center;justify-content:center;font-size:15px;cursor:pointer;transition:border-color .15s;}
.icobtn:hover{border-color:var(--white);}
.inner-main{flex:1;display:flex;flex-direction:column;overflow:hidden;background:var(--black);}
.scroll-area{flex:1;overflow-y:auto;padding:24px 28px;}
.scroll-area::-webkit-scrollbar{width:4px;}
.scroll-area::-webkit-scrollbar-thumb{background:var(--rule);}

.btn{padding:9px 18px;font-family:var(--font-main);font-weight:700;font-size:18px;border:none;transition:all .2s;display:inline-flex;align-items:center;gap:6px;cursor:pointer;}
.btn-white{background:var(--white);color:var(--black);}.btn-white:hover{background:var(--off);}
.btn-ghost{background:transparent;border:1px solid var(--rule);color:var(--muted);}.btn-ghost:hover{border-color:var(--white);color:var(--white);}
.btn-danger{background:transparent;border:1px solid #444;color:#777;}.btn-danger:hover{border-color:#999;color:#CCC;}
.page-header{margin-bottom:24px;}
.page-header h2{font-family:var(--font-pixel);font-weight:800;font-size:22px;letter-spacing:-.5px;}
.page-header p{font-size:18px;color:var(--muted);margin-top:5px;}
.divider-line{height:1px;background:var(--rule);margin:22px 0;}
.sh{display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;}
.sh-title{font-family:var(--font-pixel);font-weight:700;font-size:9px;}
.sh-more{font-size:16px;color:var(--subtle);cursor:pointer;}.sh-more:hover{color:var(--white);}
.pill{font-size:8px;font-weight:600;padding:2px 8px;border:1px solid;text-transform:uppercase;letter-spacing:.5px;font-family:var(--font-pixel)!important;}
.p-live{border-color:var(--white);color:var(--white);}.p-upcoming{border-color:var(--rule);color:var(--muted);}.p-closed{border-color:var(--rule);color:var(--rule);}

/* ─── CONTACT PAGE ─── */
#contactPage{flex-direction:row;}
.contact-grid{display:grid;grid-template-columns:1fr 320px;gap:24px;max-width:900px;}
.contact-form-card{border:3px solid #333;background:#000;padding:24px;animation:fadeUp .4s ease .05s both;}
.contact-form-card:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.15);}
.contact-form-card .form-group{margin-bottom:16px;}
.contact-form-card .form-label{display:block;font-family:var(--font-pixel);font-size:9px;color:var(--subtle);margin-bottom:7px;letter-spacing:.6px;text-transform:uppercase;}
.contact-form-card .form-input{width:100%;background:var(--ink);border:3px solid #fff;padding:10px 14px;font-family:var(--font-main);font-size:19px;color:var(--white);outline:none;transition:all .2s;}
.contact-form-card .form-input:focus{border-color:var(--ut-yellow);box-shadow:0 0 8px rgba(255,255,0,.3);}
.contact-form-card .form-input::placeholder{color:var(--muted);}
.contact-form-card select.form-input{appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='10' viewBox='0 0 10 10'%3E%3Cpath fill='%23666' d='M5 7L0 2h10z'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 13px center;padding-right:32px;}
.contact-form-card select.form-input option{background:#1A1A1A;}
.contact-form-card .form-textarea{resize:vertical;min-height:100px;line-height:1.6;}
.contact-form-card .form-row{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
.char-count{font-size:15px;color:var(--muted);text-align:right;margin-top:4px;}
.char-count.warn{color:var(--ut-yellow);}
.char-count.over{color:var(--ut-red);}
.contact-submit-btn{width:100%;background:#fff;color:#000;border:3px solid #fff;padding:13px;font-family:var(--font-pixel);font-size:9px;cursor:pointer;transition:all .2s;letter-spacing:.5px;}
.contact-submit-btn:hover{background:var(--ut-yellow);border-color:var(--ut-yellow);box-shadow:0 0 14px rgba(255,255,0,.5);}
.contact-submit-btn:disabled{background:#333;color:#666;border-color:#444;cursor:not-allowed;box-shadow:none;}
.contact-info-cards{display:flex;flex-direction:column;gap:12px;animation:fadeUp .4s ease .1s both;}
.info-card{border:3px solid #333;background:#000;padding:18px;transition:border-color .15s;}
.info-card:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.2);}
.info-card-icon{font-size:22px;margin-bottom:8px;}
.info-card-title{font-family:var(--font-pixel);font-size:9px;color:var(--ut-yellow);margin-bottom:6px;letter-spacing:.3px;}
.info-card-text{font-size:17px;color:var(--muted);line-height:1.6;}
.info-card-link{font-size:17px;color:var(--ut-cyan);display:block;margin-top:4px;cursor:pointer;}
.info-card-link:hover{color:#fff;}
.status-dot{display:inline-block;width:8px;height:8px;background:var(--ut-green);margin-right:6px;animation:blink 1.4s step-start infinite;}
.status-text{font-size:17px;color:var(--ut-green);}
.resp-bar{height:4px;background:#1a1a1a;border:2px solid #333;margin-top:8px;overflow:hidden;}
.resp-bar-fill{height:100%;background:var(--ut-yellow);width:72%;}
.contact-success{display:none;text-align:center;padding:40px 20px;animation:fadeUp .4s ease both;}
.contact-success.show{display:block;}
.contact-success-icon{font-size:48px;margin-bottom:14px;}
.contact-success-title{font-family:var(--font-pixel);font-size:11px;color:var(--ut-yellow);margin-bottom:10px;text-shadow:0 0 10px rgba(255,255,0,.3);}
.contact-success-sub{font-size:19px;color:var(--muted);margin-bottom:20px;}

/* ─── TESTIMONIALS PAGE ─── */
#testimonialsPage{flex-direction:row;}
.testi-stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:22px;animation:fadeUp .4s ease .05s both;}
.testi-stat{border:3px solid #333;background:#000;padding:14px;text-align:center;transition:border-color .15s;}
.testi-stat:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.2);}
.testi-stat-val{font-family:var(--font-pixel);font-size:13px;color:var(--ut-cyan);margin-bottom:4px;}
.testi-stat-label{font-family:var(--font-pixel);font-size:8px;color:var(--muted);letter-spacing:.3px;}
.featured-testi{border:3px solid var(--ut-yellow);background:#000;padding:24px;margin-bottom:20px;position:relative;box-shadow:5px 5px 0 rgba(255,255,0,.2);animation:fadeUp .5s ease .08s both;}
.featured-testi::before{content:'★ FEATURED';font-family:var(--font-pixel);font-size:8px;color:#000;background:var(--ut-yellow);padding:3px 8px;position:absolute;top:0;left:18px;transform:translateY(-50%);}
.featured-quote{font-size:21px;line-height:1.7;color:#fff;margin-bottom:14px;}
.featured-author{display:flex;align-items:center;gap:12px;}
.author-av{width:40px;height:40px;border:3px solid var(--ut-yellow);display:flex;align-items:center;justify-content:center;font-family:var(--font-pixel);font-size:9px;color:var(--ut-cyan);background:var(--mid);flex-shrink:0;}
.author-name{font-family:var(--font-pixel);font-size:9px;color:var(--ut-yellow);}
.author-role{font-size:16px;color:var(--muted);margin-top:3px;}
.star-row{display:flex;gap:2px;margin-top:4px;}
.star{color:var(--ut-yellow);font-size:15px;}
.star.empty{color:#333;}
.testi-filter-bar{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:18px;animation:fadeUp .4s ease .06s both;}
.testi-grid{columns:2;gap:14px;margin-bottom:20px;}
.testi-card{break-inside:avoid;border:3px solid #333;background:#000;padding:18px;margin-bottom:14px;transition:all .2s;animation:fadeUp .5s ease both;display:inline-block;width:100%;}
.testi-card:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.2);}
.testi-quote{font-size:18px;color:#e0e0e0;line-height:1.65;margin-bottom:12px;}
.testi-footer{display:flex;align-items:center;gap:9px;}
.testi-av{width:32px;height:32px;border:2px solid #444;display:flex;align-items:center;justify-content:center;font-family:var(--font-pixel);font-size:8px;color:var(--ut-cyan);background:var(--mid);flex-shrink:0;transition:border-color .15s;}
.testi-card:hover .testi-av{border-color:var(--ut-yellow);}
.testi-name{font-family:var(--font-pixel);font-size:8px;color:#fff;margin-bottom:2px;}
.testi-meta{font-size:15px;color:var(--muted);}
.testi-stars{display:flex;gap:2px;margin-top:2px;}
.testi-star{color:var(--ut-yellow);font-size:13px;}
.testi-star.empty{color:#333;}
.testi-tag{font-family:var(--font-pixel);font-size:7px;padding:2px 5px;border:2px solid;margin-left:auto;align-self:flex-start;flex-shrink:0;}
.testi-tag.voter{border-color:var(--ut-cyan);color:var(--ut-cyan);}
.testi-tag.organizer{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.testi-tag.admin{border-color:#ff4444;color:#ff4444;}
.testi-tag.student{border-color:var(--ut-green);color:var(--ut-green);}
.like-btn{background:transparent;border:2px solid #333;padding:4px 9px;font-size:14px;color:var(--muted);cursor:pointer;transition:all .15s;display:flex;align-items:center;gap:4px;margin-left:auto;font-family:var(--font-main);}
.like-btn:hover,.like-btn.liked{border-color:#ff4444;color:#ff4444;}
.write-cta{border:3px dashed #444;background:#000;padding:20px;text-align:center;margin-bottom:20px;transition:all .2s;cursor:pointer;animation:fadeUp .4s ease .12s both;}
.write-cta:hover{border-color:var(--ut-yellow);background:rgba(255,255,0,.02);}
.write-cta-icon{font-size:26px;margin-bottom:6px;}
.write-cta-title{font-family:var(--font-pixel);font-size:9px;color:var(--ut-yellow);margin-bottom:5px;}
.write-cta-sub{font-size:17px;color:var(--muted);}
.load-more-btn{display:block;width:100%;background:transparent;border:3px solid #444;color:#666;padding:13px;font-family:var(--font-pixel);font-size:9px;cursor:pointer;transition:all .2s;margin-bottom:24px;}
.load-more-btn:hover{border-color:#fff;color:#fff;}
.testi-page-header{margin-bottom:24px;padding-bottom:18px;border-bottom:3px solid #fff;animation:fadeUp .4s ease both;display:flex;align-items:flex-start;justify-content:space-between;flex-wrap:wrap;gap:14px;}
.write-review-btn{background:#fff;color:#000;border:3px solid #fff;padding:10px 16px;font-family:var(--font-pixel);font-size:8px;cursor:pointer;transition:all .2s;}
.write-review-btn:hover{background:var(--ut-yellow);border-color:var(--ut-yellow);}
.star-picker{display:flex;gap:8px;margin-bottom:4px;}
.star-pick{font-size:24px;color:#333;cursor:pointer;transition:color .1s;}
.star-pick.on{color:var(--ut-yellow);}

/* ─── CHAT WIDGET ─── */
.chat-fab{position:fixed;bottom:26px;right:26px;width:56px;height:56px;background:var(--ut-yellow);border:3px solid #fff;box-shadow:4px 4px 0 #fff;display:flex;align-items:center;justify-content:center;font-size:22px;cursor:pointer;z-index:8000;transition:all .2s;animation:fabBounce 2.5s ease infinite;}
.chat-fab:hover{transform:translate(-2px,-2px);box-shadow:6px 6px 0 #fff;}
.chat-fab-badge{position:absolute;top:-5px;right:-5px;background:var(--ut-red);color:#fff;font-family:var(--font-pixel);font-size:7px;padding:2px 4px;border:2px solid #000;min-width:16px;text-align:center;}
.chat-window{position:fixed;bottom:96px;right:26px;width:360px;height:520px;background:#000;border:4px solid #fff;box-shadow:6px 6px 0 #fff;display:flex;flex-direction:column;z-index:7999;animation:fadeUp .25s ease both;}
.chat-window.hidden{display:none;}
.chat-hdr{padding:12px 14px;border-bottom:3px solid #fff;display:flex;align-items:center;gap:10px;flex-shrink:0;background:#000;}
.chat-hdr-av{width:34px;height:34px;border:3px solid var(--ut-yellow);display:flex;align-items:center;justify-content:center;font-family:var(--font-pixel);font-size:8px;color:#000;background:var(--ut-yellow);flex-shrink:0;}
.chat-hdr-name{font-family:var(--font-pixel);font-size:9px;color:var(--ut-yellow);}
.chat-hdr-status{font-size:14px;color:var(--ut-green);display:flex;align-items:center;gap:5px;margin-top:2px;}
.chat-online-dot{width:6px;height:6px;background:var(--ut-green);animation:pulse 1.5s ease infinite;}
.chat-close-btn{width:28px;height:28px;border:3px solid #444;background:#000;display:flex;align-items:center;justify-content:center;font-size:14px;cursor:pointer;color:var(--muted);transition:all .15s;flex-shrink:0;margin-left:auto;}
.chat-close-btn:hover{border-color:#fff;color:#fff;}
.chat-msgs{flex:1;overflow-y:auto;padding:12px;display:flex;flex-direction:column;gap:9px;}
.chat-msgs::-webkit-scrollbar{width:4px!important;}
.chat-msgs::-webkit-scrollbar-thumb{background:#333!important;}
.chat-msg{max-width:88%;display:flex;flex-direction:column;gap:2px;}
.chat-msg.user{align-self:flex-end;align-items:flex-end;animation:slideIn .25s ease both;}
.chat-msg.bot{align-self:flex-start;align-items:flex-start;animation:slideInLeft .25s ease both;}
.chat-bubble{padding:9px 12px;font-size:17px;line-height:1.5;}
.chat-msg.user .chat-bubble{background:#fff;color:#000;border:3px solid #fff;}
.chat-msg.bot .chat-bubble{background:#0a0a0a;color:#fff;border:3px solid #333;}
.chat-time{font-size:13px;color:var(--muted);}
.chat-typing{display:flex;gap:4px;align-items:center;padding:3px 0;}
.chat-dot{width:6px;height:6px;background:var(--muted);animation:pulse 1s ease infinite;}
.chat-dot:nth-child(2){animation-delay:.2s;}
.chat-dot:nth-child(3){animation-delay:.4s;}
.chat-qr{padding:0 12px 8px;display:flex;gap:6px;flex-wrap:wrap;flex-shrink:0;}
.chat-qr-chip{padding:4px 10px;border:2px solid #333;color:#666;background:#000;font-size:15px;font-family:var(--font-main);cursor:pointer;transition:all .15s;}
.chat-qr-chip:hover{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.chat-input-row{border-top:3px solid #fff;padding:10px 12px;display:flex;gap:8px;flex-shrink:0;background:#000;}
.chat-input{flex:1;background:#0a0a0a;border:3px solid #fff;padding:9px 11px;font-family:var(--font-main);font-size:18px;color:#fff;outline:none;transition:border-color .2s;resize:none;max-height:70px;overflow-y:auto;line-height:1.4;}
.chat-input:focus{border-color:var(--ut-yellow);}
.chat-input::placeholder{color:var(--muted);}
.chat-send-btn{width:42px;height:42px;background:#fff;border:3px solid #fff;color:#000;font-size:16px;cursor:pointer;flex-shrink:0;transition:all .2s;display:flex;align-items:center;justify-content:center;}
.chat-send-btn:hover{background:var(--ut-yellow);border-color:var(--ut-yellow);}
.chat-send-btn:disabled{background:#333;border-color:#444;color:#666;cursor:not-allowed;}
.chat-footer-txt{border-top:2px solid #1a1a1a;padding:5px 12px;font-size:13px;color:#444;text-align:center;flex-shrink:0;}
.chat-footer-txt span{color:#555;}

#loginPage{flex-direction:row;}
.ll{width:46%;background:var(--ink);border-right:1px solid var(--rule);display:flex;flex-direction:column;justify-content:space-between;padding:48px 52px;position:relative;overflow:hidden;flex-shrink:0;}
.ll::before{content:'';position:absolute;inset:0;background-image:linear-gradient(var(--rule) 1px,transparent 1px),linear-gradient(90deg,var(--rule) 1px,transparent 1px);background-size:44px 44px;opacity:.28;}
.ll::after{content:'';position:absolute;bottom:-120px;right:-120px;width:420px;height:420px;border:1px solid var(--rule);border-radius:50%;pointer-events:none;}
.ll-top{position:relative;z-index:2;}.ll-brand{display:flex;align-items:center;gap:12px;margin-bottom:56px;animation:fadeUp .5s ease both;}
.ll-icon{width:42px;height:42px;border:1.5px solid var(--white);display:flex;align-items:center;justify-content:center;font-size:20px;}
.ll-name{font-family:var(--font-pixel);font-weight:800;font-size:22px;letter-spacing:-.5px;}
.ll-h1{font-family:var(--font-pixel);font-weight:800;font-size:46px;line-height:1.05;letter-spacing:-2px;animation:fadeUp .5s .08s ease both;}
.ll-h1 em{font-style:normal;color:var(--muted);display:block;}
.ll-p{font-size:19px;color:var(--muted);line-height:1.7;margin-top:18px;max-width:310px;animation:fadeUp .5s .14s ease both;}
.ll-bottom{position:relative;z-index:2;animation:fadeUp .5s .2s ease both;}
.ll-stats{display:flex;gap:28px;border-top:1px solid var(--rule);padding-top:22px;}
.ll-sv{font-family:var(--font-pixel);font-weight:700;font-size:20px;}.ll-sl{font-size:17px;color:var(--muted);margin-top:2px;}
.lr{flex:1;background:var(--black);display:flex;align-items:center;justify-content:center;padding:36px;overflow-y:auto;}
.lbox{width:100%;max-width:368px;}
.ltabs{display:flex;border:1px solid var(--rule);padding:3px;margin-bottom:28px;animation:fadeUp .4s ease both;}
.ltab{flex:1;padding:10px;text-align:center;font-family:var(--font-pixel);font-weight:600;font-size:9px;cursor:pointer;color:var(--muted);transition:all .2s;border:none;background:transparent;}
.ltab.active{background:var(--white);color:var(--black);}
.lfs{display:none;}.lfs.vis{display:block;}
.lh{font-family:var(--font-pixel);font-weight:700;font-size:20px;margin-bottom:4px;animation:fadeUp .4s ease both;}
.lsub{font-size:19px;color:var(--muted);margin-bottom:22px;animation:fadeUp .4s .05s ease both;}
.lf{margin-bottom:13px;animation:fadeUp .4s ease both;}
.llabel{display:block;font-size:9px;font-weight:600;color:var(--subtle);margin-bottom:6px;letter-spacing:.6px;text-transform:uppercase;font-family:var(--font-pixel)!important;}
.liw{position:relative;}
.linput{width:100%;background:var(--ink);border:1px solid var(--rule);padding:12px 14px 12px 38px;font-family:var(--font-main);font-size:20px;color:var(--white);outline:none;transition:border-color .2s;}
.linput::placeholder{color:var(--muted);}.linput:focus{border-color:var(--white);}.linput.err{border-color:#666;}
.lic{position:absolute;left:12px;top:50%;transform:translateY(-50%);font-size:15px;opacity:.4;pointer-events:none;}
.leye{position:absolute;right:12px;top:50%;transform:translateY(-50%);cursor:pointer;font-size:15px;opacity:.35;transition:opacity .2s;}
.leye:hover{opacity:.85;}
.lerr{font-size:17px;color:var(--silver);margin-top:4px;display:none;}.lerr.show{display:block;}
.lforgot{text-align:right;margin:-4px 0 14px;}.lforgot a{font-size:17px;color:var(--subtle);cursor:pointer;text-decoration:underline;}.lforgot a:hover{color:var(--white);}
.lbtn{width:100%;padding:13px;background:var(--white);border:none;font-family:var(--font-main);font-weight:700;font-size:20px;color:var(--black);cursor:pointer;transition:all .2s;display:flex;align-items:center;justify-content:center;gap:8px;margin-top:2px;}
.lbtn:hover{background:var(--off);}.lbtn:active{transform:scale(.98);}.lbtn:disabled{opacity:.5;cursor:not-allowed;}
.lbtn.ghost{background:transparent;border:1px solid var(--rule);color:var(--subtle);font-family:var(--font-main);font-weight:500;font-size:19px;}
.lbtn.ghost:hover{border-color:var(--muted);color:var(--white);background:transparent;}
.ldiv{display:flex;align-items:center;gap:10px;margin:14px 0;}.ldivl{flex:1;height:1px;background:var(--rule);}.ldivt{font-size:17px;color:var(--muted);}
.ldemo{display:flex;gap:8px;}
.lspinner{width:14px;height:14px;border:2px solid rgba(0,0,0,.2);border-top-color:var(--black);border-radius:50%!important;animation:spin .6s linear infinite;display:none;}
.l2col{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
select.linput{appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='10' viewBox='0 0 10 10'%3E%3Cpath fill='%23666' d='M5 7L0 2h10z'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 11px center;padding-right:28px;}
select.linput option{background:#1A1A1A;}
.pwbars{display:flex;gap:3px;margin-top:6px;}.pwbar{flex:1;height:3px;background:var(--rule);transition:background .3s;}.pwlabel{font-size:17px;color:var(--muted);margin-top:3px;}
.lsucc{display:none;flex-direction:column;align-items:center;text-align:center;gap:10px;}
.lsucc.vis{display:flex;animation:fadeIn .4s ease both;}
.lsucc-icon{width:64px;height:64px;border:2px solid var(--white);border-radius:50%!important;display:flex;align-items:center;justify-content:center;font-size:28px;margin-bottom:6px;animation:popIn .4s ease both;}
.lsucc-title{font-family:var(--font-pixel);font-weight:700;font-size:18px;}.lsucc-sub{font-size:19px;color:var(--muted);}
.lprogwrap{width:170px;height:8px;background:var(--rule);margin-top:14px;overflow:hidden;}.lprog{height:100%;background:var(--white);width:0%;transition:width 2.5s linear;}

#homePage{flex-direction:row;}
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:11px;margin-bottom:22px;}
.sc{background:var(--ink);border:1px solid var(--rule);padding:16px 18px;transition:border-color .2s;animation:fadeUp .4s ease both;}
.sc:hover{border-color:var(--muted);}
.sc:nth-child(1){animation-delay:.05s}.sc:nth-child(2){animation-delay:.10s}.sc:nth-child(3){animation-delay:.15s}.sc:nth-child(4){animation-delay:.20s}
.sc-label{font-size:9px;color:var(--muted);font-weight:600;letter-spacing:.6px;text-transform:uppercase;margin-bottom:7px;font-family:var(--font-pixel)!important;}
.sc-val{font-family:var(--font-pixel);font-weight:700;font-size:19px;line-height:1;}.sc-sub{font-size:17px;color:var(--subtle);margin-top:4px;}
.chips{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:18px;}
.chip{font-size:16px;padding:5px 13px;border:1px solid var(--rule);color:var(--muted);cursor:pointer;transition:all .15s;background:transparent;}.chip:hover,.chip.active{border-color:var(--white);color:var(--white);background:rgba(255,255,255,.05);}
.blist{display:flex;flex-direction:column;gap:5px;}
.bi{background:var(--ink);border:1px solid var(--rule);padding:14px 16px;display:flex;align-items:center;gap:13px;cursor:pointer;transition:all .2s;animation:fadeUp .4s ease both;}
.bi:hover{border-color:var(--muted);background:rgba(255,255,255,.02);transform:translateX(3px);}
.bico{width:38px;height:38px;border:1px solid var(--rule);display:flex;align-items:center;justify-content:center;font-size:17px;flex-shrink:0;background:var(--dark);}
.binfo{flex:1;min-width:0;}
.btitle{font-family:var(--font-main);font-weight:600;font-size:19px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;margin-bottom:2px;}
.bdesc{font-size:17px;color:var(--muted);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.bmeta{display:flex;flex-direction:column;align-items:flex-end;gap:4px;flex-shrink:0;}
.btime{font-size:16px;color:var(--muted);font-family:'Courier Prime',monospace;}
.bvotes{font-family:var(--font-pixel);font-weight:700;font-size:9px;display:flex;align-items:center;gap:5px;}
.vbw{width:48px;height:5px;background:var(--rule);overflow:hidden;}.vb{height:100%;background:var(--white);}
.fab{position:fixed;bottom:22px;right:22px;width:48px;height:48px;background:var(--white);color:var(--black);border-radius:50%!important;display:flex;align-items:center;justify-content:center;font-size:22px;font-weight:700;cursor:pointer;box-shadow:0 4px 20px rgba(0,0,0,.6);transition:transform .2s;z-index:50;}
.fab:hover{transform:scale(1.1) rotate(90deg);}

#votingPage{flex-direction:column;}
.vhdr{background:var(--ink);border-bottom:1px solid var(--rule);padding:14px 26px;display:flex;align-items:center;gap:15px;flex-shrink:0;}
.vback{display:flex;align-items:center;gap:6px;font-size:18px;color:var(--muted);cursor:pointer;padding:7px 13px;border:1px solid var(--rule);background:transparent;transition:all .15s;}
.vback:hover{color:var(--white);border-color:var(--muted);}
.vetitle{font-family:var(--font-pixel);font-weight:700;font-size:10px;}
.vemeta{font-size:16px;color:var(--muted);margin-top:2px;font-family:'Courier Prime',monospace;}
.vhdr-r{display:flex;align-items:center;gap:12px;margin-left:auto;}
.vcounter{font-family:'Courier Prime',monospace;font-size:16px;color:var(--muted);}
.vsubmit{font-family:var(--font-pixel);font-weight:700;font-size:9px;cursor:pointer;transition:all .2s;opacity:.3;pointer-events:none;}
.vsubmit.ready{opacity:1;pointer-events:all;}
.vbody{flex:1;display:flex;overflow:hidden;}
.possb{width:224px;background:var(--ink);border-right:1px solid var(--rule);overflow-y:auto;flex-shrink:0;}
.possb-hd{padding:14px 16px 8px;font-size:9px;font-weight:600;letter-spacing:1.5px;text-transform:uppercase;color:var(--muted);border-bottom:1px solid var(--rule);font-family:var(--font-pixel)!important;}
.posit{padding:13px 16px;border-bottom:1px solid var(--rule);cursor:pointer;transition:background .15s;display:flex;align-items:center;justify-content:space-between;}
.posit:hover{background:rgba(255,255,255,.03);}.posit.active{background:rgba(255,255,255,.06);}
.posit-name{font-family:var(--font-pixel);font-weight:600;font-size:8px;}
.posit-count{font-size:15px;color:var(--muted);margin-top:3px;}.posit-check{font-size:16px;}
.vcanvas{flex:1;overflow-y:auto;padding:26px 30px;background:var(--black);}
.vch{margin-bottom:22px;}
.vcpos{font-family:var(--font-pixel);font-weight:800;font-size:22px;letter-spacing:-.5px;}
.vcins{font-size:17px;color:var(--muted);margin-top:4px;}
.cgrid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:28px;}
.ccard{background:var(--ink);border:2px solid var(--rule);cursor:pointer;transition:all .2s;overflow:hidden;position:relative;animation:fadeUp .4s ease both;}
.ccard:nth-child(1){animation-delay:.05s}.ccard:nth-child(2){animation-delay:.10s}.ccard:nth-child(3){animation-delay:.15s}.ccard:nth-child(4){animation-delay:.20s}
.ccard:hover{border-color:var(--muted);transform:translateY(-2px);}.ccard.sel{border-color:var(--white);background:rgba(255,255,255,.03);}
.ccard.sel::after{content:'❤';position:absolute;top:11px;right:12px;background:transparent;color:var(--ut-heart);font-size:20px;animation:heartbeat .5s ease infinite;border:none;line-height:1;width:auto;height:auto;}
.cphoto{width:100%;aspect-ratio:4/3;background:var(--dark);border-bottom:1px solid var(--rule);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden;}
.cphoto-inner{font-size:72px;opacity:.18;user-select:none;}
.cnum{position:absolute;top:10px;left:10px;background:rgba(0,0,0,.6);border:1px solid var(--rule);font-family:'Courier Prime',monospace;font-size:11px;color:var(--muted);padding:2px 7px;}
.cbar{position:absolute;bottom:0;left:0;right:0;height:3px;}
.cinfo{padding:14px 15px 8px;}.cname{font-family:var(--font-main);font-weight:700;font-size:22px;margin-bottom:3px;}
.cparty{font-size:17px;color:var(--muted);margin-bottom:8px;}
.ctags{display:flex;gap:4px;flex-wrap:wrap;}
.ctag{font-size:14px;padding:2px 6px;border:1px solid var(--rule);color:var(--subtle);text-transform:uppercase;letter-spacing:.4px;}
.posnav{display:flex;align-items:center;gap:11px;margin-top:4px;}
.posnav-btn{padding:9px 19px;border:1px solid var(--rule);background:transparent;color:var(--muted);font-family:var(--font-main);font-size:18px;cursor:pointer;transition:all .2s;}
.posnav-btn:hover{border-color:var(--white);color:var(--white);}
.posnav-btn.pri{background:var(--white);color:var(--black);border-color:var(--white);}.posnav-btn.pri:hover{background:var(--off);}
.posnav-info{font-size:16px;color:var(--muted);font-family:'Courier Prime',monospace;}

#profilePage{flex-direction:row;}
.profile-hero{background:var(--ink);border:1px solid var(--rule);padding:28px;display:flex;align-items:center;gap:24px;margin-bottom:22px;animation:fadeUp .4s ease both;}
.profile-avatar-big{width:74px;height:74px;border:2px solid var(--white);border-radius:50%!important;display:flex;align-items:center;justify-content:center;font-family:var(--font-pixel);font-weight:800;font-size:22px;flex-shrink:0;background:var(--mid);}
.profile-name{font-family:var(--font-pixel);font-weight:800;font-size:20px;letter-spacing:-.5px;}
.profile-id{font-family:'Courier Prime',monospace;font-size:16px;color:var(--muted);margin-top:4px;}
.profile-badges{display:flex;gap:6px;margin-top:10px;flex-wrap:wrap;}
.profile-badge{font-size:16px;padding:3px 9px;border:1px solid var(--rule);color:var(--subtle);}
.profile-badge.verified{border-color:var(--white);color:var(--white);}
.pstats{display:grid;grid-template-columns:repeat(3,1fr);gap:11px;margin-bottom:22px;}
.pstat{background:var(--ink);border:1px solid var(--rule);padding:17px 18px;animation:fadeUp .4s ease both;text-align:center;}
.pstat-val{font-family:var(--font-pixel);font-weight:700;font-size:22px;}.pstat-label{font-size:17px;color:var(--muted);margin-top:4px;}
.vhist-item{background:var(--ink);border:1px solid var(--rule);padding:15px 16px;display:flex;align-items:center;gap:14px;margin-bottom:6px;animation:fadeUp .4s ease both;}
.vhist-icon{width:38px;height:38px;border:1px solid var(--rule);display:flex;align-items:center;justify-content:center;font-size:17px;flex-shrink:0;background:var(--dark);}
.vhist-info{flex:1;min-width:0;}
.vhist-title{font-family:var(--font-main);font-weight:600;font-size:18px;margin-bottom:2px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.vhist-sub{font-size:17px;color:var(--muted);}
.vhist-meta{text-align:right;flex-shrink:0;}
.vhist-date{font-family:'Courier Prime',monospace;font-size:15px;color:var(--muted);}
.cert-btn{padding:5px 10px;background:transparent;border:1px solid var(--rule);font-size:11px;color:var(--muted);cursor:pointer;transition:all .15s;margin-top:5px;display:block;font-family:var(--font-pixel)!important;}
.cert-btn:hover{border-color:var(--white);color:var(--white);}
.empty-state{color:var(--muted);font-size:18px;padding:20px 0;}
.empty-state a{color:var(--white);cursor:pointer;text-decoration:underline;}

#settingsPage{flex-direction:row;}
.settings-section{margin-bottom:26px;animation:fadeUp .4s ease both;}
.settings-section-title{font-family:var(--font-pixel);font-weight:700;font-size:9px;color:var(--subtle);letter-spacing:.8px;text-transform:uppercase;margin-bottom:10px;padding-bottom:8px;border-bottom:1px solid var(--rule);}
.settings-row{display:flex;align-items:center;justify-content:space-between;padding:14px 16px;background:var(--ink);border:1px solid var(--rule);margin-bottom:5px;transition:border-color .15s;}
.settings-row:hover{border-color:var(--muted);}
.settings-row-label{font-size:19px;font-weight:500;}.settings-row-sub{font-size:17px;color:var(--muted);margin-top:2px;}
.settings-row-ctrl{flex-shrink:0;margin-left:16px;}
.toggle{width:42px;height:22px;background:var(--rule);position:relative;cursor:pointer;transition:background .2s;}.toggle.on{background:var(--white);}
.toggle::after{content:'';position:absolute;width:16px;height:16px;background:var(--muted);border-radius:50%!important;top:3px;left:3px;transition:all .2s;}.toggle.on::after{left:23px;background:var(--black);}
.s-input{background:var(--dark);border:1px solid var(--rule);padding:8px 10px;font-family:var(--font-main);font-size:18px;color:var(--white);outline:none;transition:border-color .2s;width:180px;}
.s-input:focus{border-color:var(--white);}
select.s-input{appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='10' viewBox='0 0 10 10'%3E%3Cpath fill='%23666' d='M5 7L0 2h10z'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 9px center;padding-right:26px;}
select.s-input option{background:#1A1A1A;}

#categoriesPage{flex-direction:row;}
.cat-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:24px;}
.cat-card{background:var(--ink);border:1px solid var(--rule);padding:20px;cursor:pointer;transition:all .2s;animation:fadeUp .4s ease both;position:relative;overflow:hidden;}
.cat-card::before{content:'';position:absolute;top:-30px;right:-30px;width:80px;height:80px;border:1px solid var(--rule);border-radius:50%!important;opacity:.4;}
.cat-card:hover{border-color:var(--white);transform:translateY(-2px);}.cat-card.followed{border-color:var(--white);background:rgba(255,255,255,.04);}
.cat-icon{font-size:28px;margin-bottom:12px;}.cat-name{font-family:var(--font-pixel);font-weight:700;font-size:9px;margin-bottom:3px;}
.cat-count{font-size:16px;color:var(--muted);}.cat-desc{font-size:17px;color:var(--subtle);margin-top:6px;line-height:1.5;}
.cat-check{position:absolute;top:12px;right:12px;width:18px;height:18px;border:1px solid var(--rule);display:flex;align-items:center;justify-content:center;font-size:11px;}
.cat-card.followed .cat-check{background:var(--white);color:var(--black);border-color:var(--white);}

#addPollPage{flex-direction:row;}
.poll-form{max-width:680px;}
.form-group{margin-bottom:18px;animation:fadeUp .4s ease both;}
.form-label{display:block;font-size:9px;font-weight:600;color:var(--subtle);margin-bottom:7px;letter-spacing:.6px;text-transform:uppercase;font-family:var(--font-pixel)!important;}
.form-input{width:100%;background:var(--ink);border:1px solid var(--rule);padding:12px 14px;font-family:var(--font-main);font-size:19px;color:var(--white);outline:none;transition:border-color .2s;}
.form-input:focus{border-color:var(--white);}.form-input::placeholder{color:var(--muted);}
.form-textarea{resize:vertical;min-height:80px;line-height:1.6;}
select.form-input{appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='10' viewBox='0 0 10 10'%3E%3Cpath fill='%23666' d='M5 7L0 2h10z'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 13px center;padding-right:32px;}
select.form-input option{background:#1A1A1A;}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
input[type="datetime-local"].form-input{color-scheme:dark;}
.pos-builder{background:var(--ink);border:1px solid var(--rule);padding:16px;margin-bottom:10px;animation:fadeUp .3s ease both;}
.pos-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:13px;}
.pos-title-inp{font-family:var(--font-pixel);font-weight:700;font-size:9px;background:transparent;border:none;border-bottom:1px solid var(--rule);color:var(--white);outline:none;padding:3px 0;width:65%;transition:border-color .2s;}
.pos-title-inp:focus{border-bottom-color:var(--white);}.pos-title-inp::placeholder{color:var(--muted);}
.pos-rm{background:transparent;border:none;color:var(--muted);font-size:18px;cursor:pointer;transition:color .15s;padding:4px;}.pos-rm:hover{color:var(--white);}
.cands-list{display:flex;flex-direction:column;gap:7px;}
.cand-row{display:flex;gap:8px;align-items:center;}
.cand-inp{flex:1;background:var(--dark);border:1px solid var(--rule);padding:9px 12px;font-family:var(--font-main);font-size:18px;color:var(--white);outline:none;transition:border-color .2s;}
.cand-inp:focus{border-color:var(--white);}.cand-inp::placeholder{color:var(--muted);}
.cand-rm{background:transparent;border:none;color:var(--muted);font-size:16px;cursor:pointer;transition:color .15s;}.cand-rm:hover{color:var(--white);}
.add-cand-btn{background:transparent;border:1px dashed var(--rule);padding:8px 12px;font-size:18px;color:var(--muted);cursor:pointer;transition:all .15s;width:100%;margin-top:4px;font-family:var(--font-main);}
.add-cand-btn:hover{border-color:var(--white);color:var(--white);}
.add-pos-btn{background:transparent;border:1px dashed var(--rule);padding:15px;font-size:18px;color:var(--muted);cursor:pointer;transition:all .15s;width:100%;font-family:var(--font-main);display:flex;align-items:center;justify-content:center;gap:8px;margin-bottom:22px;}
.add-pos-btn:hover{border-color:var(--white);color:var(--white);}
.poll-preview{background:var(--ink);border:1px solid var(--rule);padding:18px;position:sticky;top:0;}
.preview-title{font-family:var(--font-pixel);font-weight:700;font-size:9px;margin-bottom:12px;padding-bottom:8px;border-bottom:1px solid var(--rule);color:var(--subtle);letter-spacing:.5px;text-transform:uppercase;}
.preview-item{padding:9px 11px;background:var(--dark);border:1px solid var(--rule);margin-bottom:5px;}
.preview-pos{font-family:var(--font-pixel);font-weight:600;font-size:8px;margin-bottom:3px;}.preview-cands{font-size:17px;color:var(--muted);}

.moverlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.88);z-index:200;align-items:center;justify-content:center;}
.moverlay.show{display:flex;}
.mbox{background:var(--ink);border:1px solid var(--rule);padding:30px;width:90%;max-width:450px;animation:fadeUp .3s ease both;}
.mtitle{font-family:var(--font-pixel);font-weight:700;font-size:17px;margin-bottom:5px;}.msub{font-size:18px;color:var(--muted);margin-bottom:20px;}
.msum{display:flex;flex-direction:column;gap:8px;margin-bottom:20px;}
.mrow{display:flex;align-items:center;justify-content:space-between;padding:10px 14px;background:var(--dark);border:1px solid var(--rule);}
.mpos{font-size:16px;color:var(--muted);}.mcand{font-family:var(--font-main);font-weight:600;font-size:18px;}
.macts{display:flex;gap:9px;}
.mcancel{flex:1;padding:11px;border:1px solid var(--rule);background:transparent;color:var(--muted);font-size:18px;cursor:pointer;transition:all .15s;font-family:var(--font-main);}
.mcancel:hover{color:var(--white);border-color:var(--muted);}
.mconfirm{flex:2;padding:11px;border:none;background:var(--white);color:var(--black);font-family:var(--font-main);font-weight:700;font-size:20px;cursor:pointer;}
.mconfirm:hover{background:var(--off);}
.cert-box{background:var(--dark);border:1px solid var(--rule);padding:18px;margin-bottom:16px;font-family:'Courier Prime',monospace;font-size:16px;color:var(--silver);line-height:1.85;}
.cert-box strong{color:var(--white);}.cert-hash{word-break:break-all;color:var(--muted);font-size:15px;margin-top:10px;padding-top:10px;border-top:1px solid var(--rule);}

.toast{position:fixed;bottom:22px;left:50%;transform:translateX(-50%) translateY(80px);background:var(--ink);border:1px solid var(--rule);padding:10px 18px;font-size:19px;color:var(--white);box-shadow:0 4px 24px rgba(0,0,0,.7);transition:transform .3s cubic-bezier(.34,1.56,.64,1);z-index:500;white-space:nowrap;display:flex;align-items:center;gap:8px;}
.toast.show{transform:translateX(-50%) translateY(0);}

@media(max-width:700px){.ll{display:none;}.cgrid{grid-template-columns:1fr;}.stats-grid{grid-template-columns:1fr 1fr;}.cat-grid{grid-template-columns:1fr;}.form-row{grid-template-columns:1fr;}.contact-grid{grid-template-columns:1fr;}.testi-grid{columns:1;}.testi-stats-row{grid-template-columns:1fr 1fr;}}

/* ── ACCESSIBILITY: focus rings & skip link ── */
:focus-visible{outline:3px solid var(--ut-yellow)!important;outline-offset:2px!important;}
.skip-link{position:fixed;top:-60px;left:16px;background:var(--ut-yellow);color:#000;padding:10px 18px;font-family:var(--font-pixel);font-size:9px;z-index:99999;transition:top .2s;}
.skip-link:focus{top:10px;}
/* Ensure muted text meets contrast on interactive elements */
.sb-it{color:#bbb!important;}
.sb-it:hover,.sb-it.active{color:#fff!important;}
.settings-row-sub{color:#aaa!important;}
.bdesc{color:#aaa!important;}
.sc-sub{color:#aaa!important;}
.info-card-text{color:#aaa!important;}

/* ── ABOUT PAGE ── */
#aboutPage{flex-direction:row;}
.about-hero{background:#000;border:3px solid var(--ut-yellow);padding:36px;margin-bottom:24px;position:relative;overflow:hidden;box-shadow:6px 6px 0 rgba(255,255,0,.2);animation:fadeUp .5s ease both;}
.about-hero::before{content:'';position:absolute;inset:0;background-image:linear-gradient(#1a1a1a 1px,transparent 1px),linear-gradient(90deg,#1a1a1a 1px,transparent 1px);background-size:32px 32px;opacity:.4;pointer-events:none;}
.about-hero-inner{position:relative;z-index:1;}
.about-hero-tag{font-family:var(--font-pixel);font-size:8px;color:var(--ut-cyan);border:2px solid var(--ut-cyan);padding:3px 10px;display:inline-block;margin-bottom:14px;}
.about-hero-title{font-family:var(--font-pixel);font-size:18px;color:var(--ut-yellow);text-shadow:0 0 20px rgba(255,255,0,.5);line-height:2;margin-bottom:10px;}
.about-hero-sub{font-size:21px;color:#ddd;line-height:1.7;max-width:680px;margin-bottom:24px;}
.about-hero-btns{display:flex;gap:12px;flex-wrap:wrap;}
.about-hero-btn{padding:12px 22px;font-family:var(--font-pixel);font-size:9px;cursor:pointer;transition:all .2s;border:3px solid;}
.about-hero-btn.primary{background:var(--ut-yellow);color:#000;border-color:var(--ut-yellow);}
.about-hero-btn.primary:hover{background:#fff;border-color:#fff;box-shadow:0 0 14px rgba(255,255,255,.4);}
.about-hero-btn.ghost{background:transparent;color:#fff;border-color:#fff;}
.about-hero-btn.ghost:hover{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.about-stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:28px;animation:fadeUp .4s ease .06s both;}
.about-stat{border:3px solid #333;background:#000;padding:18px;text-align:center;transition:all .2s;}
.about-stat:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.2);}
.about-stat-val{font-family:var(--font-pixel);font-size:16px;color:var(--ut-cyan);margin-bottom:5px;}
.about-stat-label{font-family:var(--font-pixel);font-size:8px;color:#aaa;letter-spacing:.3px;}
.about-section{margin-bottom:28px;animation:fadeUp .4s ease .08s both;}
.about-section-title{font-family:var(--font-pixel);font-size:10px;color:var(--ut-yellow);margin-bottom:14px;padding-bottom:10px;border-bottom:3px solid #333;}
.about-features-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:8px;}
.about-feature{border:3px solid #333;background:#000;padding:20px;transition:all .2s;}
.about-feature:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.15);}
.about-feature-icon{font-size:28px;margin-bottom:10px;}
.about-feature-title{font-family:var(--font-pixel);font-size:9px;color:#fff;margin-bottom:7px;}
.about-feature-desc{font-size:17px;color:#aaa;line-height:1.6;}
.about-team-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;}
.about-team-card{border:3px solid #333;background:#000;padding:20px;text-align:center;transition:all .2s;}
.about-team-card:hover{border-color:var(--ut-yellow);box-shadow:0 0 10px rgba(255,255,0,.2);}
.about-team-av{width:56px;height:56px;border:3px solid var(--ut-yellow);display:flex;align-items:center;justify-content:center;font-family:var(--font-pixel);font-size:12px;color:var(--ut-cyan);background:var(--mid);margin:0 auto 12px;}
.about-team-name{font-family:var(--font-pixel);font-size:9px;color:#fff;margin-bottom:4px;}
.about-team-role{font-size:16px;color:#aaa;margin-bottom:8px;}
.about-team-badge{font-family:var(--font-pixel);font-size:7px;padding:2px 7px;border:2px solid var(--ut-cyan);color:var(--ut-cyan);display:inline-block;}
.about-tech-row{display:flex;gap:10px;flex-wrap:wrap;margin-top:4px;}
.about-tech-pill{font-family:var(--font-pixel);font-size:8px;padding:4px 10px;border:2px solid #333;color:#aaa;transition:all .15s;}
.about-tech-pill:hover{border-color:var(--ut-yellow);color:var(--ut-yellow);}
.about-mission{border:3px solid #333;background:#000;padding:24px;margin-bottom:14px;position:relative;}
.about-mission::before{content:'"';font-family:var(--font-main);font-size:80px;color:var(--ut-yellow);opacity:.15;position:absolute;top:10px;left:18px;line-height:1;}
.about-mission-text{font-size:21px;color:#ddd;line-height:1.8;position:relative;z-index:1;padding-left:12px;}

@media(max-width:700px){.about-features-grid{grid-template-columns:1fr;}.about-team-grid{grid-template-columns:1fr 1fr;}.about-stats-row{grid-template-columns:1fr 1fr;}}
</style>
</head>
<body>
<a href="#main-content" class="skip-link">Skip to main content</a>

<!-- LOGIN -->
<div class="page active" id="loginPage">
  <div class="ll">
    <div class="ll-top">
      <div class="ll-brand"><div class="ll-icon">🗳</div><div class="ll-name">SkibiVote</div></div>
      <h1 class="ll-h1">YOUR VOTE<em>FILLED WITH</em><em style="color:var(--ut-heart)">DETERMINATION.</em></h1>
      <p class="ll-p">* You are filled with DETERMINATION. Cast your vote and shape the future of your community.</p>
    </div>
    <div class="ll-bottom"><div class="ll-stats">
      <div><div class="ll-sv">67k+</div><div class="ll-sl">SOULS</div></div>
      <div><div class="ll-sv">99.9%</div><div class="ll-sl">UPTIME</div></div>
      <div><div class="ll-sv">0</div><div class="ll-sl">Issues</div></div>
    </div></div>
  </div>
  <div class="lr"><div class="lbox">
    <div class="ltabs">
      <button class="ltab active" id="tabLogin" onclick="lSwitch('login')">Sign In</button>
      <button class="ltab" id="tabReg" onclick="lSwitch('register')">Register</button>
    </div>
    <div class="lfs vis" id="lLogin">
      <div class="lh">* HUMAN appeared!</div>
      <div class="lsub">What will you do? (please log in)</div>
      <div class="lf"><label class="llabel" for="lid">Voter ID or Email</label><div class="liw"><span class="lic" aria-hidden="true">👤</span><input type="text" class="linput" id="lid" placeholder="voter or you@email.com" aria-label="Voter ID or Email address" autocomplete="username"></div><div class="lerr" id="lidErr" role="alert">Enter your ID or email.</div></div>
      <div class="lf"><label class="llabel" for="lpw">Password</label><div class="liw"><span class="lic" aria-hidden="true">🔑</span><input type="password" class="linput" id="lpw" placeholder="Enter password" aria-label="Password" autocomplete="current-password"><span class="leye" onclick="lToggle('lpw',this)" aria-label="Toggle password visibility" role="button" tabindex="0">👁</span></div><div class="lerr" id="lpwErr" role="alert">Invalid credentials.</div></div>
      <div class="lforgot"><a onclick="toast('📧 Reset link sent!')" role="button" tabindex="0">Forgot password?</a></div>
      <button class="lbtn" id="lLoginBtn" onclick="lDoLogin()" aria-label="Sign in to SkibiVote"><div class="lspinner" id="lLoginSpinner" aria-hidden="true"></div><span id="lLoginBtnTxt">Sign In →</span></button>
      <div class="ldiv"><div class="ldivl"></div><div class="ldivt">quick demo</div><div class="ldivl"></div></div>
      <div class="ldemo"><button class="lbtn ghost" onclick="lDemo('voter')">❤ VOTER</button><button class="lbtn ghost" onclick="lDemo('admin')">★ ADMIN</button></div>
    </div>
    <div class="lfs" id="lReg">
      <div class="lh">* A new SOUL appears!</div><div class="lsub">Register to begin your journey</div>
      <div class="l2col">
        <div class="lf"><label class="llabel">First Name</label><div class="liw"><span class="lic">✏️</span><input type="text" class="linput" id="rfirst" placeholder="Jerome Irvin"></div><div class="lerr" id="rfirstErr">Required.</div></div>
        <div class="lf"><label class="llabel">Last Name</label><div class="liw"><span class="lic">✏️</span><input type="text" class="linput" id="rlast" placeholder="De Jesus"></div><div class="lerr" id="rlastErr">Required.</div></div>
      </div>
      <div class="lf"><label class="llabel">Email</label><div class="liw"><span class="lic">📧</span><input type="email" class="linput" id="remail" placeholder="you@email.com"></div><div class="lerr" id="remailErr">Valid email required.</div></div>
      <div class="lf"><label class="llabel">Barangay</label><div class="liw"><span class="lic">📍</span>
        <select class="linput" id="rbar"><option value="" disabled selected>Select barangay</option>
          <option>Almanza Uno</option><option>Almanza Dos</option><option>CAA/BBF</option><option>Daniel Fajardo</option><option>Ilaya</option><option>Manuyo Uno</option><option>Manuyo Dos</option><option>Pamplona Uno</option><option>Pamplona Dos</option><option>Pamplona Tres</option><option>Pilar</option><option>Pulang Lupa Uno</option><option>Pulang Lupa Dos</option><option>Talon Uno</option><option>Talon Dos</option><option>Talon Tres</option><option>Talon Kuatro</option><option>Talon Singko</option><option>Zapote</option>
        </select>
      </div><div class="lerr" id="rbarErr">Select your barangay.</div></div>
      <div class="lf"><label class="llabel">Password</label><div class="liw"><span class="lic">🔑</span><input type="password" class="linput" id="rpw" placeholder="Min 8 characters" oninput="lStrength(this.value)"><span class="leye" onclick="lToggle('rpw',this)">👁</span></div><div class="lerr" id="rpwErr">At least 8 characters.</div><div class="pwbars"><div class="pwbar" id="pb1"></div><div class="pwbar" id="pb2"></div><div class="pwbar" id="pb3"></div><div class="pwbar" id="pb4"></div></div><div class="pwlabel" id="pwlbl"></div></div>
      <div class="lf"><label class="llabel">Confirm Password</label><div class="liw"><span class="lic">🔒</span><input type="password" class="linput" id="rconf" placeholder="Repeat password"><span class="leye" onclick="lToggle('rconf',this)">👁</span></div><div class="lerr" id="rconfErr">Passwords don't match.</div></div>
      <button class="lbtn" id="lRegBtn" onclick="lDoReg()"><div class="lspinner" id="lRegSpinner"></div><span id="lRegBtnTxt">Create Account →</span></button>
    </div>
    <div class="lsucc" id="lSucc">
      <div class="lsucc-icon">✓</div>
      <div class="lsucc-title" id="lSuccT">Welcome!</div>
      <div class="lsucc-sub" id="lSuccS">Redirecting…</div>
      <div class="lprogwrap"><div class="lprog" id="lprog"></div></div>
    </div>
  </div></div>
</div>

<!-- HOME -->
<div class="page" id="homePage">
  <aside class="sb" id="homeSB"></aside>
  <div class="inner-main">
    <div class="topbar">
      <div class="topbar-title">Elections &amp; Polls</div>
      <div class="sw"><span class="sico">🔍</span><input type="text" class="sinput" placeholder="Search…" oninput="filterBallots(this.value)"></div>
      <div class="tbr"><div class="icobtn" title="Add Poll" onclick="goAddPoll()">＋</div><div class="icobtn">🔔</div></div>
    </div>
    <div class="scroll-area">
      <div class="stats-grid">
        <div class="sc"><div class="sc-label">Active Elections</div><div class="sc-val" id="hActiveCount">3</div><div class="sc-sub">Live now</div></div>
        <div class="sc"><div class="sc-label">Total Voters</div><div class="sc-val">67k+</div><div class="sc-sub">4.2% turnout</div></div>
        <div class="sc"><div class="sc-label">Your Status</div><div class="sc-val">✓ Verified</div><div class="sc-sub">Ready to vote</div></div>
        <div class="sc"><div class="sc-label">Votes Cast</div><div class="sc-val" id="hBallotCount">0</div><div class="sc-sub" id="hBallotSub">Get voting!</div></div>
      </div>
      <div class="chips">
        <div class="chip active" onclick="chipF(this,'all')">All</div>
        <div class="chip" onclick="chipF(this,'national')">National</div>
        <div class="chip" onclick="chipF(this,'local')">Local</div>
        <div class="chip" onclick="chipF(this,'barangay')">Barangay</div>
        <div class="chip" onclick="chipF(this,'school')">School</div>
        <div class="chip" onclick="chipF(this,'org')">Organization</div>
      </div>
      <div class="section-divider">
        <div class="section-divider-label">🏛 OFFICIAL ELECTIONS</div>
        <div class="section-divider-line"></div>
      </div>
      <div class="blist" id="blistElections"></div>
      <div class="section-divider polls-divider" style="margin-top:28px;">
        <div class="section-divider-label" style="color:var(--ut-cyan)!important;">📋 COMMUNITY POLLS</div>
        <div class="section-divider-line"></div>
        <div class="sh-more" onclick="goAddPoll()" style="white-space:nowrap;font-size:16px;color:var(--subtle);cursor:pointer;">+ Add Poll</div>
      </div>
      <div class="blist" id="blistPolls"></div>
    </div>
  </div>
  <div class="fab" onclick="goAddPoll()">+</div>
</div>

<!-- VOTING -->
<div class="page" id="votingPage">
  <div class="vhdr">
    <button class="vback" onclick="goHome()">← Back</button>
    <div><div class="vetitle" id="vetitle">Election</div><div class="vemeta" id="vemeta">Live</div></div>
    <div class="vhdr-r"><div class="vcounter" id="vcounter">0 / 0 filled</div><button class="vsubmit" id="vsubmit" onclick="openModal()">Submit Vote →</button></div>
  </div>
  <div class="vbody">
    <div class="possb" id="possb"><div class="possb-hd">Positions</div></div>
    <div class="vcanvas">
      <div class="vch"><div class="vcpos" id="vcpos">Position</div><div class="vcins" id="vcins">Select 1 candidate</div></div>
      <div class="cgrid" id="cgrid"></div>
      <div class="posnav">
        <button class="posnav-btn" id="prevBtn" onclick="changePosIdx(-1)">← Previous</button>
        <div class="posnav-info" id="posnavinfo">1 of 1</div>
        <button class="posnav-btn pri" id="nextBtn" onclick="changePosIdx(1)">Next →</button>
      </div>
    </div>
  </div>
</div>

<!-- RESULTS -->
<div class="page" id="resultsPage">
  <aside class="sb" id="resultsSB"></aside>
  <div class="inner-main">
    <div class="topbar">
      <div class="topbar-title">Results</div>
      <div class="tbr"><div class="icobtn" title="Refresh" onclick="renderResults()">↻</div></div>
    </div>
    <div class="scroll-area" id="resultsScroll"></div>
  </div>
</div>

<!-- PROFILE -->
<div class="page" id="profilePage">
  <aside class="sb" id="profileSB"></aside>
  <div class="inner-main">
    <div class="topbar"><div class="topbar-title">My Profile</div><div class="tbr"><div class="icobtn" onclick="goSettings()" title="Settings">⚙️</div></div></div>
    <div class="scroll-area">
      <div class="profile-hero">
        <div class="profile-avatar-big" id="profAv">JI</div>
        <div style="flex:1">
          <div class="profile-name" id="profName">—</div>
          <div class="profile-id" id="profId">—</div>
          <div class="profile-badges" id="profBadges"></div>
        </div>
        <button class="btn btn-ghost" onclick="goSettings()">Edit Profile</button>
      </div>
      <div class="pstats">
        <div class="pstat" style="animation-delay:.05s"><div class="pstat-val" id="profVoted">0</div><div class="pstat-label">Elections Voted</div></div>
        <div class="pstat" style="animation-delay:.10s"><div class="pstat-val" id="profPending">0</div><div class="pstat-label">Pending Votes</div></div>
        <div class="pstat" style="animation-delay:.15s"><div class="pstat-val" id="profCreated">0</div><div class="pstat-label">Polls Created</div></div>
      </div>
      <div class="sh"><div class="sh-title">Vote History</div></div>
      <div id="vHistList"></div>
      <div class="divider-line"></div>
      <div class="sh"><div class="sh-title">Polls I Created</div><div class="sh-more" onclick="goAddPoll()">+ New Poll</div></div>
      <div id="createdList"></div>
    </div>
  </div>
</div>

<!-- SETTINGS -->
<div class="page" id="settingsPage">
  <aside class="sb" id="settingsSB"></aside>
  <div class="inner-main">
    <div class="topbar"><div class="topbar-title">Settings</div></div>
    <div class="scroll-area">
      <div class="settings-section" style="animation-delay:.05s">
        <div class="settings-section-title">Account Information</div>
        <div class="settings-row"><div><div class="settings-row-label">Full Name</div><div class="settings-row-sub" id="sName">—</div></div><div class="settings-row-ctrl"><button class="btn btn-ghost" style="padding:5px 11px;font-size:16px;" onclick="openEdit('name','Full Name')">Edit</button></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Email Address</div><div class="settings-row-sub" id="sEmail">—</div></div><div class="settings-row-ctrl"><button class="btn btn-ghost" style="padding:5px 11px;font-size:16px;" onclick="openEdit('email','Email')">Edit</button></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Barangay</div><div class="settings-row-sub" id="sBarangay">—</div></div><div class="settings-row-ctrl"><button class="btn btn-ghost" style="padding:5px 11px;font-size:16px;" onclick="openEdit('barangay','Barangay')">Edit</button></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Password</div><div class="settings-row-sub">••••••••</div></div><div class="settings-row-ctrl"><button class="btn btn-ghost" style="padding:5px 11px;font-size:16px;" onclick="toast('📧 Password reset link sent!')">Change</button></div></div>
      </div>
      <div class="settings-section" style="animation-delay:.10s">
        <div class="settings-section-title">Notifications</div>
        <div class="settings-row"><div><div class="settings-row-label">Email Notifications</div><div class="settings-row-sub">New elections in your categories</div></div><div class="settings-row-ctrl"><div class="toggle on" id="tog1" onclick="toggleSetting(this)"></div></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Election Reminders</div><div class="settings-row-sub">Before elections close</div></div><div class="settings-row-ctrl"><div class="toggle on" id="tog2" onclick="toggleSetting(this)"></div></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Result Announcements</div><div class="settings-row-sub">When results are published</div></div><div class="settings-row-ctrl"><div class="toggle" id="tog3" onclick="toggleSetting(this)"></div></div></div>
        <div class="settings-row"><div><div class="settings-row-label">New Poll Alerts</div><div class="settings-row-sub">Polls in your followed categories</div></div><div class="settings-row-ctrl"><div class="toggle on" id="tog4" onclick="toggleSetting(this)"></div></div></div>
      </div>
      <div class="settings-section" style="animation-delay:.15s">
        <div class="settings-section-title">Privacy &amp; Security</div>
        <div class="settings-row"><div><div class="settings-row-label">Two-Factor Authentication</div><div class="settings-row-sub">Extra security for your account</div></div><div class="settings-row-ctrl"><div class="toggle" id="tog5" onclick="toggleSetting(this)"></div></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Anonymous Votes</div><div class="settings-row-sub">Keep your votes private in results</div></div><div class="settings-row-ctrl"><div class="toggle on" id="tog6" onclick="toggleSetting(this)"></div></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Login Activity</div><div class="settings-row-sub">Last login: just now</div></div><div class="settings-row-ctrl"><button class="btn btn-ghost" style="padding:5px 11px;font-size:16px;" onclick="toast('Showing login history…')">View</button></div></div>
      </div>
      <div class="settings-section" style="animation-delay:.20s">
        <div class="settings-section-title">Display Preferences</div>
        <div class="settings-row"><div><div class="settings-row-label">Language</div></div><div class="settings-row-ctrl"><select class="s-input" onchange="toast('Language updated ✓')"><option>English</option><option>Filipino</option><option>Cebuano</option></select></div></div>
        <div class="settings-row"><div><div class="settings-row-label">Results View</div></div><div class="settings-row-ctrl"><select class="s-input" onchange="toast('Preference saved ✓')"><option>Bar chart</option><option>Percentage only</option><option>Numbers only</option></select></div></div>
      </div>
      <div class="settings-section" style="animation-delay:.25s">
        <div class="settings-section-title">Danger Zone</div>
        <div class="settings-row"><div><div class="settings-row-label">Export My Data</div><div class="settings-row-sub">Download all your data as JSON</div></div><div class="settings-row-ctrl"><button class="btn btn-ghost" style="padding:5px 11px;font-size:16px;" onclick="exportData()">Export</button></div></div>
        <div class="settings-row"><div><div class="settings-row-label" style="color:#888">Delete Account</div><div class="settings-row-sub">Permanently remove everything</div></div><div class="settings-row-ctrl"><button class="btn btn-danger" style="padding:5px 11px;font-size:16px;" onclick="toast('Contact support to delete your account.')">Delete</button></div></div>
      </div>
      <button class="btn btn-ghost" onclick="goLogin()"><span>🚪</span> Sign Out</button>
    </div>
  </div>
</div>

<!-- CATEGORIES -->
<div class="page" id="categoriesPage">
  <aside class="sb" id="categoriesSB"></aside>
  <div class="inner-main">
    <div class="topbar"><div class="topbar-title">Categories</div></div>
    <div class="scroll-area">
      <div class="page-header"><h2>Browse by Category</h2><p>Follow categories to get notified about new elections.</p></div>
      <div class="cat-grid" id="catGrid"></div>
      <div class="divider-line"></div>
      <div class="sh"><div class="sh-title">Elections in Followed Categories</div></div>
      <div class="blist" id="catBlist"></div>
    </div>
  </div>
</div>

<!-- ADD POLL -->
<div class="page" id="addPollPage">
  <aside class="sb" id="addPollSB"></aside>
  <div class="inner-main">
    <div class="topbar">
      <div class="topbar-title">Create New Poll</div>
      <div class="tbr"><button class="btn btn-ghost" style="padding:7px 14px;font-size:17px;" onclick="goHome()">✕ Cancel</button></div>
    </div>
    <div class="scroll-area">
      <div style="display:grid;grid-template-columns:1fr 310px;gap:24px;align-items:start;">
        <div class="poll-form">
          <div class="page-header"><h2>Poll Details</h2><p>Fill in the election info, then add positions and candidates below.</p></div>
          <div class="form-group" style="animation-delay:.05s"><label class="form-label">Poll Title *</label><input type="text" class="form-input" id="pollTitle" placeholder="e.g. 2025 Barangay Council Elections" oninput="updatePreview()"></div>
          <div class="form-group" style="animation-delay:.08s"><label class="form-label">Description</label><textarea class="form-input form-textarea" id="pollDesc" placeholder="Describe the purpose of this election…" oninput="updatePreview()"></textarea></div>
          <div class="form-row">
            <div class="form-group" style="animation-delay:.11s"><label class="form-label">Category *</label>
              <select class="form-input" id="pollCat" onchange="onCatChange()">
                <option value="" disabled selected>Select category</option>
                <option value="national">National</option><option value="local">Local</option><option value="barangay">Barangay</option><option value="school">School</option><option value="org">Organization</option>
              </select>
            </div>
            <div class="form-group" style="animation-delay:.11s"><label class="form-label">Type</label>
              <select class="form-input" id="pollType"><option value="poll">Community Poll</option><option value="election">Official Election</option></select>
            </div>
          </div>
          <div class="form-row">
            <div class="form-group" style="animation-delay:.14s"><label class="form-label">Start Date &amp; Time *</label><input type="datetime-local" class="form-input" id="pollStart"></div>
            <div class="form-group" style="animation-delay:.14s"><label class="form-label">End Date &amp; Time *</label><input type="datetime-local" class="form-input" id="pollEnd"></div>
          </div>
          <div class="divider-line"></div>
          <div class="sh" style="margin-bottom:14px"><div class="sh-title">Positions &amp; Candidates</div></div>
          <div class="pos-preset-panel" id="presetPanel" style="display:none;">
            <div class="pos-preset-header" onclick="togglePresetPanel()">
              <div>
                <div class="pos-preset-title">⚡ Quick-Add Preset Positions</div>
                <div class="pos-preset-subtitle">Click a position to add it instantly</div>
              </div>
              <span id="presetArrow" style="font-size:18px;color:var(--muted);">▼</span>
            </div>
            <div class="pos-preset-body" id="presetBody"></div>
          </div>
          <div id="posContainer"></div>
          <button class="add-pos-btn" onclick="addPos()">＋ Add Custom Position</button>
          <div style="display:flex;gap:10px;">
            <button class="btn btn-white" onclick="submitPoll('live')" style="flex:1;justify-content:center;">Publish Poll →</button>
            <button class="btn btn-ghost" onclick="submitPoll('draft')">Save Draft</button>
          </div>
        </div>
        <div class="poll-preview">
          <div class="preview-title">Live Preview</div>
          <div id="pollPreviewBody"><div style="color:var(--muted);font-size:17px;">Fill in the form to see a preview…</div></div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ───── CONTACT PAGE ───── -->
<div class="page" id="contactPage">
  <aside class="sb" id="contactSB"></aside>
  <div class="inner-main">
    <div class="topbar">
      <div class="topbar-title">* CONTACT US</div>
      <div class="tbr"><div class="icobtn">🔔</div></div>
    </div>
    <div class="scroll-area">
      <div class="page-header">
        <h2>* GET IN TOUCH</h2>
        <p>Questions, feedback, bug reports — we actually read these.</p>
      </div>
      <div class="contact-grid">
        <div class="contact-form-card">
          <div id="contactFormArea">
            <div class="section-divider"><span class="section-divider-label">SEND A MESSAGE</span><div class="section-divider-line"></div></div>
            <div class="contact-form-card form-row">
              <div class="form-group"><label class="form-label">Your Name</label><input id="cName" class="form-input" type="text" placeholder="Juan dela Cruz"></div>
              <div class="form-group"><label class="form-label">Email Address</label><input id="cEmail" class="form-input" type="email" placeholder="juan@example.com"></div>
            </div>
            <div class="form-group"><label class="form-label">Subject</label>
              <select id="cSubject" class="form-input">
                <option value="">— Select a topic —</option>
                <option value="bug">🐛 Report a Bug</option>
                <option value="feature">✨ Feature Request</option>
                <option value="account">👤 Account Issue</option>
                <option value="election">🗳 Election / Poll Help</option>
                <option value="press">📰 Press Inquiry</option>
                <option value="other">💬 Other</option>
              </select>
            </div>
            <div class="form-group">
              <label class="form-label">Message</label>
              <textarea id="cMsg" class="form-input form-textarea" placeholder="Describe your issue or question in detail…" maxlength="800" oninput="updateCharCount()"></textarea>
              <div id="cCharCount" class="char-count">0 / 800</div>
            </div>
            <div class="form-group" style="display:flex;align-items:center;gap:10px;padding:11px 13px;border:3px solid #333;background:#0a0a0a;">
              <input type="checkbox" id="cCopy" style="width:18px;height:18px;accent-color:var(--ut-yellow);">
              <label for="cCopy" style="font-size:17px;color:var(--muted);">Send me a copy of this message</label>
            </div>
            <button class="contact-submit-btn" id="cSubmitBtn" onclick="submitContact()">[ SEND MESSAGE ]</button>
          </div>
          <div class="contact-success" id="contactSuccess">
            <div class="contact-success-icon">✉️</div>
            <div class="contact-success-title">* MESSAGE SENT!</div>
            <div class="contact-success-sub">We'll get back to you within 24–48 hours.<br>Check your inbox for a confirmation.</div>
            <button class="btn btn-ghost" style="margin:0 auto;" onclick="resetContact()">[ Send Another Message ]</button>
          </div>
        </div>
        <div class="contact-info-cards">
          <div class="info-card">
            <div class="info-card-icon">📡</div>
            <div class="info-card-title">SYSTEM STATUS</div>
            <div class="status-text"><span class="status-dot"></span>All systems operational</div>
            <div class="resp-bar"><div class="resp-bar-fill"></div></div>
            <div style="font-size:15px;color:var(--muted);margin-top:5px;">Uptime: 99.8% — Last 30 days</div>
          </div>
          <div class="info-card">
            <div class="info-card-icon">⏱</div>
            <div class="info-card-title">RESPONSE TIME</div>
            <div class="info-card-text">We typically reply within <span style="color:var(--ut-yellow);">24–48 hours</span> on weekdays.</div>
          </div>
          <div class="info-card">
            <div class="info-card-icon">📧</div>
            <div class="info-card-title">DIRECT EMAIL</div>
            <div class="info-card-text">For urgent matters:</div>
            <span class="info-card-link">support@skibivote.ph</span>
          </div>
          <div class="info-card">
            <div class="info-card-icon">📜</div>
            <div class="info-card-title">BEFORE YOU WRITE</div>
            <div class="info-card-text">
              <span class="info-card-link">📚 Read the FAQ</span>
              <span class="info-card-link">🗺 Check the Roadmap</span>
              <span class="info-card-link">🐞 Known Issues</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ───── TESTIMONIALS PAGE ───── -->
<div class="page" id="testimonialsPage">
  <aside class="sb" id="testimonialsSB"></aside>
  <div class="inner-main">
    <div class="topbar">
      <div class="topbar-title">* TESTIMONIALS</div>
      <div class="tbr"><div class="icobtn">🔔</div></div>
    </div>
    <div class="scroll-area">
      <div class="testi-page-header">
        <div>
          <h2 style="font-family:var(--font-pixel);font-size:11px;color:var(--ut-yellow);text-shadow:0 0 10px rgba(255,255,0,.3);margin-bottom:6px;">* WHAT VOTERS SAY</h2>
          <p style="font-size:18px;color:var(--muted);">Real feedback from real election participants.</p>
        </div>
        <button class="write-review-btn" onclick="openWriteModal()">[ + Write a Review ]</button>
      </div>
      <div class="testi-stats-row">
        <div class="testi-stat"><div class="testi-stat-val">4.9</div><div class="testi-stat-label">AVG RATING</div></div>
        <div class="testi-stat"><div class="testi-stat-val">2,841</div><div class="testi-stat-label">REVIEWS</div></div>
        <div class="testi-stat"><div class="testi-stat-val">98%</div><div class="testi-stat-label">RECOMMEND</div></div>
        <div class="testi-stat"><div class="testi-stat-val">147</div><div class="testi-stat-label">ELECTIONS HELD</div></div>
      </div>
      <div class="testi-filter-bar" id="testiFilterBar">
        <span class="chip active" onclick="testiFilter(this,'all')">All Reviews</span>
        <span class="chip" onclick="testiFilter(this,'voter')">👤 Voters</span>
        <span class="chip" onclick="testiFilter(this,'organizer')">🏛 Organizers</span>
        <span class="chip" onclick="testiFilter(this,'student')">🎓 Students</span>
        <span class="chip" onclick="testiFilter(this,'admin')">⚙ Admins</span>
        <span class="chip" onclick="testiFilter(this,'5')">★★★★★ 5-star</span>
      </div>
      <div class="featured-testi">
        <div class="featured-quote">"SkibiVote completely transformed how our student council runs elections. We went from paper votes counted by hand to a live results dashboard — voter turnout jumped from 40% to 91% in one semester."</div>
        <div class="featured-author">
          <div class="author-av">CM</div>
          <div>
            <div class="author-name">CARLA MENDOZA ✓</div>
            <div class="author-role">Student Council Adviser — UP Diliman</div>
            <div class="star-row"><span class="star">★</span><span class="star">★</span><span class="star">★</span><span class="star">★</span><span class="star">★</span></div>
          </div>
        </div>
      </div>
      <div class="write-cta" onclick="openWriteModal()">
        <div class="write-cta-icon">✍️</div>
        <div class="write-cta-title">SHARE YOUR EXPERIENCE</div>
        <div class="write-cta-sub">Voted or organized? Tell the community what you think.</div>
      </div>
      <div class="section-divider"><span class="section-divider-label">ALL REVIEWS</span><div class="section-divider-line"></div></div>
      <div class="testi-grid" id="testiGrid"></div>
      <button class="load-more-btn" id="testiLoadMoreBtn" onclick="testiLoadMore()">[ LOAD MORE REVIEWS ]</button>
    </div>
  </div>
</div>

<!-- ───── ABOUT PAGE ───── -->
<div class="page" id="aboutPage" role="main" id="main-content">
  <aside class="sb" id="aboutSB" role="navigation" aria-label="Main navigation"></aside>
  <div class="inner-main">
    <div class="topbar">
      <div class="topbar-title" role="heading" aria-level="1">* ABOUT SKIBIVOTE</div>
      <div class="tbr"><div class="icobtn" onclick="goHome()" title="Go to home" aria-label="Go to home">🏠</div></div>
    </div>
    <div class="scroll-area" id="main-content">

      <!-- HERO -->
      <div class="about-hero" role="banner">
        <div class="about-hero-inner">
          <div class="about-hero-tag">* EST. 2025 — LAS PIÑAS CITY, PH</div>
          <div class="about-hero-title">DEMOCRACY,<br>PIXEL BY PIXEL.</div>
          <p class="about-hero-sub">SkibiVote is a modern, retro-styled online voting platform built to make elections transparent, accessible, and tamper-resistant — for barangays, schools, organizations, and communities across the Philippines.</p>
          <div class="about-hero-btns">
            <button class="about-hero-btn primary" onclick="goHome()" aria-label="Start voting now">[ Start Voting → ]</button>
            <button class="about-hero-btn ghost" onclick="goContact()" aria-label="Contact the team">[ Contact Us ]</button>
          </div>
        </div>
      </div>

      <!-- STATS -->
      <div class="about-stats-row" role="region" aria-label="Platform statistics">
        <div class="about-stat"><div class="about-stat-val">67k+</div><div class="about-stat-label">REGISTERED VOTERS</div></div>
        <div class="about-stat"><div class="about-stat-val">147</div><div class="about-stat-label">ELECTIONS HELD</div></div>
        <div class="about-stat"><div class="about-stat-val">99.9%</div><div class="about-stat-label">UPTIME</div></div>
        <div class="about-stat"><div class="about-stat-val">0</div><div class="about-stat-label">FRAUD CASES</div></div>
      </div>

      <!-- MISSION -->
      <div class="about-section" role="region" aria-label="Mission statement">
        <div class="about-section-title">* OUR MISSION</div>
        <div class="about-mission">
          <p class="about-mission-text">To empower every Filipino — from barangay residents to university students — with a secure, accessible, and transparent digital voting experience that upholds the integrity of democratic processes at every level of society.</p>
        </div>
      </div>

      <!-- FEATURES -->
      <div class="about-section" role="region" aria-label="Platform features">
        <div class="about-section-title">* WHAT WE OFFER</div>
        <div class="about-features-grid">
          <div class="about-feature">
            <div class="about-feature-icon" aria-hidden="true">🗳</div>
            <div class="about-feature-title">SECURE VOTING</div>
            <p class="about-feature-desc">Every vote is cryptographically hashed and timestamped. Votes cannot be altered, deleted, or duplicated once cast.</p>
          </div>
          <div class="about-feature">
            <div class="about-feature-icon" aria-hidden="true">📊</div>
            <div class="about-feature-title">LIVE RESULTS</div>
            <p class="about-feature-desc">Watch results update in real-time as votes come in. Animated bar charts and percentage breakdowns for every position.</p>
          </div>
          <div class="about-feature">
            <div class="about-feature-icon" aria-hidden="true">🏛</div>
            <div class="about-feature-title">MULTI-LEVEL ELECTIONS</div>
            <p class="about-feature-desc">Supports national, local, barangay, school, and organizational elections — with preset positions for each level.</p>
          </div>
          <div class="about-feature">
            <div class="about-feature-icon" aria-hidden="true">📜</div>
            <div class="about-feature-title">VOTE CERTIFICATES</div>
            <p class="about-feature-desc">Every voter receives a downloadable certificate with a unique verification hash as proof of their participation.</p>
          </div>
          <div class="about-feature">
            <div class="about-feature-icon" aria-hidden="true">📋</div>
            <div class="about-feature-title">COMMUNITY POLLS</div>
            <p class="about-feature-desc">Anyone can create a community poll in minutes. Gather feedback from your neighborhood, school, or organization.</p>
          </div>
          <div class="about-feature">
            <div class="about-feature-icon" aria-hidden="true">♿</div>
            <div class="about-feature-title">ACCESSIBLE BY DESIGN</div>
            <p class="about-feature-desc">Built with keyboard navigation, screen reader support, skip links, high-contrast UI, and ARIA labels throughout.</p>
          </div>
        </div>
      </div>

      <!-- TEAM -->
      <div class="about-section" role="region" aria-label="Development team">
        <div class="about-section-title">* THE TEAM</div>
        <div class="about-team-grid">
          <div class="about-team-card">
            <div class="about-team-av" aria-hidden="true">JJ</div>
            <div class="about-team-name">Jerome Irvin De Jesus</div>
            <div class="about-team-role">Project Lead</div>
            <span class="about-team-badge">LEAD DEV</span>
          </div>
          <div class="about-team-card">
            <div class="about-team-av" aria-hidden="true">MM</div>
            <div class="about-team-name">Mary Gwyneth Meude</div>
            <div class="about-team-role">UI Ideas, Bug Finder/Fixer, Tester</div>
            <span class="about-team-badge">DESIGN</span>
          </div>
          <div class="about-team-card">
            <div class="about-team-av" aria-hidden="true">MJ</div>
            <div class="about-team-name">Maverick Jose</div>
            <div class="about-team-role">Bug Finder/Fixer, Tester</div>
            <span class="about-team-badge">ASSIST DEV</span>
          </div>
          <div class="about-team-card">
            <div class="about-team-av" aria-hidden="true">LN</div>
            <div class="about-team-name">Luke Neri</div>
            <div class="about-team-role">Bug Finder/Fixer</div>
            <span class="about-team-badge">ASSIST DEV</span>
          </div>
          <div class="about-team-card">
            <div class="about-team-av" aria-hidden="true">EV</div>
            <div class="about-team-name">Erhyl Ivan Valencia</div>
            <div class="about-team-role">Bug Finder/Fixer, Tester</div>
            <span class="about-team-badge">ASSIST DEV</span>
          </div>
          <div class="about-team-card">
            <div class="about-team-av" aria-hidden="true">EJ</div>
            <div class="about-team-name">Edjivic Joseph Ybanez</div>
            <div class="about-team-role">Bug Finder/Fixer, Tester</div>
            <span class="about-team-badge">ASSIST DEV</span>
          </div>
        </div>
      </div>

      <!-- TECH STACK -->
      <div class="about-section" role="region" aria-label="Technology stack">
        <div class="about-section-title">* BUILT WITH</div>
        <div class="about-tech-row" role="list">
          <div class="about-tech-pill" role="listitem">HTML5</div>
          <div class="about-tech-pill" role="listitem">CSS3</div>
          <div class="about-tech-pill" role="listitem">Vanilla JS</div>
          <div class="about-tech-pill" role="listitem">AI Chat API</div>
          <div class="about-tech-pill" role="listitem">VT323 Font</div>
          <div class="about-tech-pill" role="listitem">Press Start 2P</div>
          <div class="about-tech-pill" role="listitem">Google Fonts</div>
          <div class="about-tech-pill" role="listitem">ARIA / WCAG</div>
          <div class="about-tech-pill" role="listitem">Responsive Design</div>
        </div>
      </div>

      <!-- COURSE INFO -->
      <div class="about-section" role="region" aria-label="Course information">
        <div class="about-section-title">* COURSE INFORMATION</div>
        <div class="about-mission" style="border-color:var(--ut-cyan);">
          <p class="about-mission-text" style="font-size:18px;">
            <span style="color:var(--ut-cyan);">Subject:</span> Human-Computer Interaction (HCI)<br>
            <span style="color:var(--ut-cyan);">Project:</span> Web Application System Design<br>
            <span style="color:var(--ut-cyan);">System:</span> E-Voting Platform (SkibiVote)<br>
            <span style="color:var(--ut-cyan);">Institution:</span> Las Piñas City, Philippines<br>
            <span style="color:var(--ut-cyan);">Academic Year:</span> 2025–2026
          </p>
        </div>
      </div>

    </div>
  </div>
</div>

<!-- MODALS -->
<div class="moverlay" id="modalVote">
  <div class="mbox">
    <div class="mtitle">Confirm Your Vote</div>
    <div class="msub">Review before submitting. This cannot be undone.</div>
    <div class="msum" id="msum"></div>
    <div class="macts"><button class="mcancel" onclick="closeModal('modalVote')">Review Again</button><button class="mconfirm" onclick="doSubmit()">✓ Submit Vote</button></div>
  </div>
</div>
<div class="moverlay" id="modalCert">
  <div class="mbox" style="max-width:490px;">
    <div class="mtitle">🗳 Vote Certificate</div>
    <div class="msub">Official proof of your participation in this election.</div>
    <div class="cert-box" id="certContent"></div>
    <div class="macts"><button class="mcancel" onclick="closeModal('modalCert')">Close</button><button class="mconfirm" onclick="toast('📄 Certificate downloaded!');closeModal('modalCert')">Download PDF</button></div>
  </div>
</div>
<div class="moverlay" id="modalEdit">
  <div class="mbox" style="max-width:370px;">
    <div class="mtitle" id="editTitle">Edit Field</div>
    <div class="msub" id="editSub">—</div>
    <input type="text" class="form-input" id="editInput" style="margin-bottom:18px;">
    <div class="macts"><button class="mcancel" onclick="closeModal('modalEdit')">Cancel</button><button class="mconfirm" onclick="saveEdit()">Save Changes</button></div>
  </div>
</div>

<!-- WRITE REVIEW MODAL -->
<div class="moverlay" id="modalReview">
  <div class="mbox" style="max-width:480px;">
    <div class="mtitle">* WRITE YOUR REVIEW</div>
    <div class="msub" style="font-size:17px;">Share your honest experience with SkibiVote.</div>
    <div style="margin-bottom:14px;">
      <div style="font-family:var(--font-pixel);font-size:9px;color:var(--subtle);margin-bottom:7px;letter-spacing:.6px;">YOUR RATING</div>
      <div class="star-picker" id="starPicker">
        <span class="star-pick" onclick="setStars(1)">★</span>
        <span class="star-pick" onclick="setStars(2)">★</span>
        <span class="star-pick" onclick="setStars(3)">★</span>
        <span class="star-pick" onclick="setStars(4)">★</span>
        <span class="star-pick" onclick="setStars(5)">★</span>
      </div>
    </div>
    <div style="margin-bottom:14px;"><div style="font-family:var(--font-pixel);font-size:9px;color:var(--subtle);margin-bottom:7px;letter-spacing:.6px;">YOUR NAME</div><input id="rName" class="form-input" type="text" placeholder="Display name"></div>
    <div style="margin-bottom:14px;"><div style="font-family:var(--font-pixel);font-size:9px;color:var(--subtle);margin-bottom:7px;letter-spacing:.6px;">ROLE</div>
      <select id="rRole" class="form-input">
        <option value="voter">Voter</option><option value="organizer">Election Organizer</option><option value="student">Student</option><option value="admin">Admin</option>
      </select>
    </div>
    <div style="margin-bottom:18px;"><div style="font-family:var(--font-pixel);font-size:9px;color:var(--subtle);margin-bottom:7px;letter-spacing:.6px;">YOUR REVIEW</div><textarea id="rText" class="form-input form-textarea" placeholder="Share your experience with SkibiVote…"></textarea></div>
    <div class="macts"><button class="mcancel" onclick="closeModal('modalReview')">[ Cancel ]</button><button class="mconfirm" onclick="submitReview()">[ Submit Review ]</button></div>
  </div>
</div>

<div class="toast" id="toastEl" role="status" aria-live="polite" aria-atomic="true"><span id="toastMsg">Done!</span></div>

<!-- ───── CHAT WIDGET (always visible after login) ───── -->
<div class="chat-fab hidden" id="chatFab" onclick="toggleChat()">
  💬
  <div class="chat-fab-badge" id="chatFabBadge">1</div>
</div>
<div class="chat-window hidden" id="chatWindow">
  <div class="chat-hdr">
    <div class="chat-hdr-av">SV</div>
    <div style="flex:1">
      <div class="chat-hdr-name">SKIBIVOTE SUPPORT</div>
      <div class="chat-hdr-status"><div class="chat-online-dot"></div> Online — AI-powered</div>
    </div>
    <div class="chat-close-btn" onclick="toggleChat()">—</div>
    <div class="chat-close-btn" onclick="closeChat()" style="margin-left:4px;">✕</div>
  </div>
  <div class="chat-msgs" id="chatMsgs"></div>
  <div class="chat-qr" id="chatQR">
    <div class="chat-qr-chip" onclick="chatQuick('How do I create an election?')">Create election</div>
    <div class="chat-qr-chip" onclick="chatQuick('How do I vote?')">How to vote</div>
    <div class="chat-qr-chip" onclick="chatQuick('I found a bug')">Report bug</div>
    <div class="chat-qr-chip" onclick="chatQuick('Show me results')">Results</div>
  </div>
  <div class="chat-input-row">
    <textarea class="chat-input" id="chatInputEl" placeholder="Type a message…" rows="1" onkeydown="chatHandleKey(event)" oninput="chatAutoResize(this)"></textarea>
    <button class="chat-send-btn" id="chatSendBtn" onclick="chatSend()">➤</button>
  </div>
  <div class="chat-footer-txt">SkibiVote Support Bot · 24/7</div>
</div>

<script>
// ── IN-MEMORY STATE ──
var _state = {
  curUser: null,
  users: [
    {id:'voter',email:'voter@skibivote.ph',password:'voter123',name:'Jerome Irvin De Jesus',role:'voter',barangay:'Pamplona Uno'},
    {id:'admin',email:'admin@skibivote.ph',password:'admin123',name:'Admin User',role:'admin',barangay:'Zapote'},
  ],
  voteHistory: {}, userPolls: {}, followed: {}, settings: {},
};
function getCurUser(){ return _state.curUser; }
function setCurUser(u){ _state.curUser = u; }
function uid(){ return getCurUser() ? getCurUser().id : 'anon'; }
function getUsers(){ return _state.users; }
function saveUsers(u){ _state.users = u; }
function getHistory(){ return _state.voteHistory[uid()] || []; }
function addHistory(e){ if(!_state.voteHistory[uid()]) _state.voteHistory[uid()]=[];  _state.voteHistory[uid()].unshift(e); }
function getUserPolls(){ return _state.userPolls[uid()] || []; }
function saveUserPolls(p){ _state.userPolls[uid()] = p; }
function getFollowed(){ return _state.followed[uid()] || ['local','barangay']; }
function saveFollowed(c){ _state.followed[uid()] = c; }
function getSettings(){ return _state.settings[uid()] || {}; }
function saveSettings(s){ _state.settings[uid()] = s; }

// ── POSITION PRESETS ──
var POSITION_PRESETS = {
  barangay:{label:'🏘 Barangay Level',positions:['Punong Barangay (Barangay Captain)','Barangay Kagawad — Education','Barangay Kagawad — Health','Barangay Kagawad — Infrastructure','Barangay Kagawad — Peace & Order','Barangay Kagawad — Finance','Barangay Kagawad — Livelihood','Barangay Kagawad — Environment','Barangay Secretary','Barangay Treasurer','SK Chairperson','SK Kagawad']},
  local:{label:'🏙 City / Municipal Level',positions:['Mayor','Vice Mayor','City Councilor (1st District)','City Councilor (2nd District)','City Councilor (3rd District)','City Councilor (At-Large)','City Secretary','City Treasurer','Liga ng mga Barangay President','SK Federation President']},
  national:{label:'🏛 National Level',positions:['President','Vice President','Senator (1st Seat)','Senator (2nd Seat)','Senator (3rd Seat)','Senator (4th Seat)','Senator (5th Seat)','Senator (6th Seat)','District Representative','Party-List Representative']},
  school:{label:'🎓 School / University Level',positions:['SSC / SBM President','SSC / SBM Vice President','SSC Secretary','SSC Treasurer','SSC Auditor','SSC PRO','SSC Business Manager','Class President','Class Vice President','Class Secretary','College Governor','College Deputy Governor']},
  org:{label:'🏢 Organization / HOA Level',positions:['President','Vice President','Secretary','Treasurer','Auditor','Board of Director','PRO (Public Relations Officer)','Committee Chair — Finance','Committee Chair — Events','Committee Chair — Security']},
};

// ── ELECTION DATA ──
var ELECTIONS = [
  {id:1,icon:'🏛',title:'2025 Barangay Council Elections',desc:'Barangay 123, Las Piñas City',time:'27m ago',votes:'67k+',pct:72,status:'live',tag:'barangay',type:'election',createdBy:'system',
    positions:[
      {name:'Punong Barangay (Barangay Captain)',pick:1,candidates:[
        {name:'Maria Santos',party:'Lakas ng Bayan',tags:['Incumbent','Education'],votes:8420},
        {name:'Roberto Cruz',party:'Bagong Alyansa',tags:['Infrastructure','Youth'],votes:6150},
        {name:'Ana Reyes',party:'Pagbabago',tags:['Health','Women'],votes:4200},
        {name:'Jose Dela Cruz',party:'Independyente',tags:['Anti-Graft','Business'],votes:2900},
      ]},
      {name:'Barangay Kagawad — Education',pick:1,candidates:[
        {name:'Liza Fernandez',party:'Lakas ng Bayan',tags:['Teacher','Youth'],votes:7100},
        {name:'Danilo Ramos',party:'Bagong Alyansa',tags:['Engineer'],votes:5500},
        {name:'Carla Mendoza',party:'Pagbabago',tags:['Nurse','Women'],votes:4400},
        {name:'Ryan Aquino',party:'Independyente',tags:['Lawyer'],votes:3000},
      ]},
      {name:'Barangay Kagawad — Health',pick:1,candidates:[
        {name:'Noel Bautista',party:'Lakas ng Bayan',tags:['Doctor'],votes:9200},
        {name:'Grace Villanueva',party:'Bagong Alyansa',tags:['Midwife'],votes:5100},
        {name:'Mark Pascual',party:'Pagbabago',tags:['Safety'],votes:3300},
        {name:'Elena Torres',party:'Independyente',tags:['Pharmacist'],votes:2100},
      ]},
      {name:'SK Chairperson',pick:1,candidates:[
        {name:'Nico Domingo',party:'Kabataan Pilipinas',tags:['Student','Sports'],votes:5500},
        {name:'Aira Salazar',party:'Bagong Henerasyon',tags:['Activist','Arts'],votes:4800},
        {name:'Brian Flores',party:'Youth First',tags:['Scholar','Tech'],votes:3900},
        {name:'Trisha Morales',party:'Pagbabago',tags:['Leader'],votes:2200},
      ]},
    ]},
  {id:2,icon:'🎓',title:'Student Government Elections',desc:'PLM — AY 2025–2026',time:'2h ago',votes:'12k+',pct:55,status:'live',tag:'school',type:'election',createdBy:'system',
    positions:[{name:'SSC / SBM President',pick:1,candidates:[
      {name:'Clara Santos',party:'Unity Party',tags:['Honor Student'],votes:3400},
      {name:'Marco Reyes',party:'Progressive',tags:['Debate'],votes:2800},
      {name:'Pia Cruz',party:'Lakas Estudyante',tags:['Sports'],votes:2100},
      {name:'Dino Aquino',party:'Independent',tags:['Research'],votes:1700},
    ]}]},
  {id:3,icon:'🏢',title:'HOA Officer Elections',desc:'Annual HOA — Phase 3 Subdivision',time:'5h ago',votes:'890',pct:44,status:'live',tag:'org',type:'election',createdBy:'system',
    positions:[{name:'President',pick:1,candidates:[
      {name:'Ricardo Tan',party:'Homeowners First',tags:['Security'],votes:240},
      {name:'Mylene Ong',party:'New Leadership',tags:['Finance'],votes:200},
      {name:'Albert Go',party:'Independent',tags:['Legal'],votes:160},
      {name:'Susan Lee',party:'Community First',tags:['Events'],votes:120},
    ]}]},
  {id:4,icon:'📣',title:'Municipal Budget Referendum',desc:'Infrastructure spending FY 2026',time:'1d ago',votes:'34k+',pct:88,status:'upcoming',tag:'local',type:'election',createdBy:'system',positions:[]},
  {id:5,icon:'📖',title:'Curriculum Reform — School Board',desc:'Parent & teacher vote on curriculum',time:'3d ago',votes:'2.8k',pct:61,status:'closed',tag:'school',type:'election',createdBy:'system',
    positions:[{name:'Curriculum Reform Stance',pick:1,candidates:[
      {name:'For Reform',party:'Parent Alliance',tags:['Progressive'],votes:1680},
      {name:'Against Reform',party:'Traditional',tags:['Conservative'],votes:820},
      {name:'Abstain',party:'Neutral',tags:[],votes:300},
    ]}]},
];
var POLLS = [
  {id:101,icon:'🌿',title:'Environmental Policy Survey',desc:'Community park development input',time:'2d ago',votes:'4.1k',pct:30,status:'live',tag:'local',type:'poll',createdBy:'system',positions:[
    {name:'Preferred Park Feature',pick:1,candidates:[
      {name:'Jogging Track',party:'Option A',tags:['Fitness'],votes:980},
      {name:'Playground',party:'Option B',tags:['Kids'],votes:850},
      {name:'Garden & Benches',party:'Option C',tags:['Relaxation'],votes:720},
      {name:'Basketball Court',party:'Option D',tags:['Sports'],votes:610},
    ]}
  ]},
  {id:102,icon:'🍜',title:'Community Canteen Menu Vote',desc:'What should the canteen add next month?',time:'5h ago',votes:'523',pct:65,status:'closed',tag:'barangay',type:'poll',createdBy:'system',positions:[
    {name:'New Menu Item',pick:1,candidates:[
      {name:'Sinigang na Baboy',party:'Option A',tags:['Classic'],votes:180},
      {name:'Palabok',party:'Option B',tags:['Noodles'],votes:140},
      {name:'Kare-Kare',party:'Option C',tags:['Specialty'],votes:110},
      {name:'Lechon Kawali',party:'Option D',tags:['Crispy'],votes:93},
    ]}
  ]},
];
var CATEGORIES = [
  {id:'national',icon:'🏛',name:'National',desc:'Nationwide government elections & referendums',count:2},
  {id:'local',icon:'🏙',name:'Local',desc:'City, municipal and provincial elections',count:5},
  {id:'barangay',icon:'🏘',name:'Barangay',desc:'Barangay council and SK elections',count:8},
  {id:'school',icon:'🎓',name:'School',desc:'Student government and school board elections',count:4},
  {id:'org',icon:'🏢',name:'Organization',desc:'HOA, clubs and organizational elections',count:3},
  {id:'survey',icon:'📊',name:'Surveys',desc:'Community polls and public consultations',count:6},
];

function allElections(){ return ELECTIONS.concat(getUserPolls()); }
function allElectionsOnly(){ return allElections().filter(function(e){ return e.type==='election'||!e.type; }); }
function allPollsOnly(){ return POLLS.concat(getUserPolls().filter(function(p){ return p.type==='poll'; })); }
function allBallots(){ return ELECTIONS.concat(POLLS).concat(getUserPolls()); }

var lTab = 'login';

// ── SIDEBAR ──
function buildSB(id, active){
  var u = getCurUser() || {name:'User',id:'—',role:'voter'};
  var parts = u.name.split(' ');
  var ini = parts.map(function(w){ return w[0]; }).slice(0,2).join('');
  var short = parts[0] + ' ' + (parts[1] ? parts[1][0] + '.' : '');
  var liveCount = allElections().filter(function(e){ return e.status==='live' && e.positions && e.positions.length; }).length;
  document.getElementById(id).innerHTML =
    '<div class="sb-logo"><div class="sb-li" aria-hidden="true">🗳</div><div class="sb-ln">SkibiVote</div></div>' +
    '<div class="sb-user"><div class="sb-av" aria-hidden="true">'+ini+'</div><div><div class="sb-un">'+short+'</div><div class="sb-ur">'+(u.role==='admin'?'Administrator':'Verified Voter')+'</div></div></div>' +
    '<nav class="sb-nav" aria-label="Main navigation">' +
    '<div class="sb-sec">Menu</div>' +
    '<div class="sb-it '+(active==='home'?'active':'')+'" onclick="goHome()" role="button" tabindex="0" aria-label="Home" aria-current="'+(active==='home'?'page':'false')+'"><span aria-hidden="true">🏠</span> Home</div>' +
    '<div class="sb-it" onclick="goVoteNow()" role="button" tabindex="0" aria-label="Vote now"><span aria-hidden="true">🗳</span> Vote Now <span class="sb-badge" aria-label="'+liveCount+' live elections">'+liveCount+'</span></div>' +
    '<div class="sb-it '+(active==='results'?'active':'')+'" onclick="goResults()" role="button" tabindex="0" aria-label="Results" aria-current="'+(active==='results'?'page':'false')+'"><span aria-hidden="true">📊</span> Results</div>' +
    '<div class="sb-it '+(active==='addpoll'?'active':'')+'" onclick="goAddPoll()" role="button" tabindex="0" aria-label="Add Poll" aria-current="'+(active==='addpoll'?'page':'false')+'"><span aria-hidden="true">➕</span> Add Poll</div>' +
    '<div class="sb-sec" style="margin-top:5px">Browse</div>' +
    '<div class="sb-it '+(active==='categories'?'active':'')+'" onclick="goCategories()" role="button" tabindex="0" aria-label="Categories" aria-current="'+(active==='categories'?'page':'false')+'"><span aria-hidden="true">🏷</span> Categories</div>' +
    '<div class="sb-sec" style="margin-top:5px">Community</div>' +
    '<div class="sb-it '+(active==='testimonials'?'active':'')+'" onclick="goTestimonials()" role="button" tabindex="0" aria-label="Testimonials" aria-current="'+(active==='testimonials'?'page':'false')+'"><span aria-hidden="true">⭐</span> Testimonials</div>' +
    '<div class="sb-it '+(active==='contact'?'active':'')+'" onclick="goContact()" role="button" tabindex="0" aria-label="Contact us" aria-current="'+(active==='contact'?'page':'false')+'"><span aria-hidden="true">✉</span> Contact</div>' +
    '<div class="sb-it '+(active==='about'?'active':'')+'" onclick="goAbout()" role="button" tabindex="0" aria-label="About SkibiVote" aria-current="'+(active==='about'?'page':'false')+'"><span aria-hidden="true">ℹ</span> About</div>' +
    '<div class="sb-sec" style="margin-top:5px">Account</div>' +
    '<div class="sb-it '+(active==='profile'?'active':'')+'" onclick="goProfile()" role="button" tabindex="0" aria-label="My Profile" aria-current="'+(active==='profile'?'page':'false')+'"><span aria-hidden="true">👤</span> Profile</div>' +
    '<div class="sb-it '+(active==='settings'?'active':'')+'" onclick="goSettings()" role="button" tabindex="0" aria-label="Settings" aria-current="'+(active==='settings'?'page':'false')+'"><span aria-hidden="true">⚙️</span> Settings</div>' +
    '</nav>' +
    '<div class="sb-foot"><div class="sb-logout" onclick="goLogin()" role="button" tabindex="0" aria-label="Log out"><span aria-hidden="true">🚪</span> Log Out</div></div>';
}

function showPage(id){
  document.querySelectorAll('.page').forEach(function(p){ p.classList.remove('active'); });
  document.getElementById(id).classList.add('active');
}

// ── NAVIGATION ──
function goLogin(){ setCurUser(null); document.getElementById('chatFab').classList.add('hidden'); closeChat(); showPage('loginPage'); }

function goVoteNow(){
  var el = allElections().find(function(e){ return e.positions && e.positions.length && e.status==='live'; });
  if(el) goVoting(el);
  else toast('No active elections to vote on right now.');
}

function goHome(){
  buildSB('homeSB','home');
  renderBlist();
  var h = getHistory();
  var live = allElections().filter(function(e){ return e.status==='live' && e.positions && e.positions.length; }).length;
  document.getElementById('hActiveCount').textContent = live;
  document.getElementById('hBallotCount').textContent = h.length;
  document.getElementById('hBallotSub').textContent = h.length > 0 ? h.length+' cast' : 'Get voting!';
  showPage('homePage');
  document.getElementById('chatFab').classList.remove('hidden');
}

function goVoting(el){
  if(!el || !el.positions || !el.positions.length){ toast('No votes available for this election.'); return; }
  curEl = el; curPosIdx = 0; votes = {};
  document.getElementById('vetitle').textContent = el.title;
  document.getElementById('vemeta').textContent = (el.status==='live'?'Live':el.status) + ' · ' + el.votes + ' voters · ' + el.time;
  renderPosSb(); renderCands(); updCounter();
  showPage('votingPage');
}

function goResults(){
  buildSB('resultsSB','results');
  curResElection = null; curResFilter = 'all';
  renderResults();
  showPage('resultsPage');
}

function goProfile(){ buildSB('profileSB','profile'); renderProfile(); showPage('profilePage'); }

function goSettings(){
  buildSB('settingsSB','settings');
  var u = getCurUser();
  if(u){
    document.getElementById('sName').textContent = u.name;
    document.getElementById('sEmail').textContent = u.email;
    document.getElementById('sBarangay').textContent = u.barangay || '—';
  }
  showPage('settingsPage');
}

function goCategories(){ buildSB('categoriesSB','categories'); renderCategories(); showPage('categoriesPage'); }

function goAddPoll(){
  buildSB('addPollSB','addpoll');
  var pc = document.getElementById('posContainer');
  if(!pc.children.length) addPos();
  var n = new Date(); n.setMinutes(0,0,0);
  var en = new Date(n); en.setDate(en.getDate()+7);
  document.getElementById('pollStart').value = n.toISOString().slice(0,16);
  document.getElementById('pollEnd').value = en.toISOString().slice(0,16);
  showPage('addPollPage');
}

function goContact(){
  buildSB('contactSB','contact');
  showPage('contactPage');
}

function goTestimonials(){
  buildSB('testimonialsSB','testimonials');
  renderTestimonials();
  showPage('testimonialsPage');
}

function goAbout(){
  buildSB('aboutSB','about');
  showPage('aboutPage');
}

// ── LOGIN ──
function lSwitch(t){
  lTab = t;
  document.getElementById('lLogin').classList.toggle('vis', t==='login');
  document.getElementById('lReg').classList.toggle('vis', t==='register');
  document.getElementById('lSucc').classList.remove('vis');
  document.getElementById('tabLogin').classList.toggle('active', t==='login');
  document.getElementById('tabReg').classList.toggle('active', t==='register');
  document.querySelectorAll('.linput').forEach(function(i){ i.classList.remove('err'); });
  document.querySelectorAll('.lerr').forEach(function(e){ e.classList.remove('show'); });
}
function lToggle(id, el){
  var i = document.getElementById(id);
  i.type = i.type === 'password' ? 'text' : 'password';
  el.style.opacity = i.type === 'text' ? '.85' : '.35';
}
function lStrength(v){
  var s = 0;
  if(v.length >= 8) s++;
  if(/[A-Z]/.test(v)) s++;
  if(/[0-9]/.test(v)) s++;
  if(/[^A-Za-z0-9]/.test(v)) s++;
  var c = ['#555','#888','#AAA','#FFF'];
  var l = ['Weak','Fair','Good','Strong'];
  [1,2,3,4].forEach(function(n){ document.getElementById('pb'+n).style.background = n<=s ? c[s-1] : 'var(--rule)'; });
  var lb = document.getElementById('pwlbl');
  lb.textContent = v.length ? (l[s-1]||'') : '';
  lb.style.color = s>0 ? c[s-1] : 'var(--muted)';
}
function lErr(id, msg){
  var i = document.getElementById(id);
  var e = document.getElementById(id+'Err');
  if(i) i.classList.add('err');
  if(e){ if(msg) e.textContent = msg; e.classList.add('show'); }
}
function lDemo(t){
  document.getElementById('lid').value = t;
  document.getElementById('lpw').value = t+'123';
  toast('Demo credentials filled ✓');
}
function lSuccAnim(title, sub){
  document.getElementById('lLogin').classList.remove('vis');
  document.getElementById('lReg').classList.remove('vis');
  var succ = document.getElementById('lSucc');
  succ.classList.add('vis');
  document.getElementById('lSuccT').textContent = title;
  document.getElementById('lSuccS').textContent = sub;
  var prog = document.getElementById('lprog');
  prog.style.width = '0%';
  setTimeout(function(){ prog.style.width = '100%'; }, 50);
}
function lSetBusy(isLogin, busy){
  var btnId = isLogin ? 'lLoginBtn' : 'lRegBtn';
  var spinnerId = isLogin ? 'lLoginSpinner' : 'lRegSpinner';
  var txtId = isLogin ? 'lLoginBtnTxt' : 'lRegBtnTxt';
  var defaultTxt = isLogin ? 'Sign In →' : 'Create Account →';
  document.getElementById(btnId).disabled = busy;
  document.getElementById(spinnerId).style.display = busy ? 'block' : 'none';
  document.getElementById(txtId).textContent = busy ? 'Please wait…' : defaultTxt;
}
function lDoLogin(){
  var id = document.getElementById('lid').value.trim();
  var pw = document.getElementById('lpw').value;
  var ok = true;
  document.querySelectorAll('.linput').forEach(function(i){ i.classList.remove('err'); });
  document.querySelectorAll('.lerr').forEach(function(e){ e.classList.remove('show'); });
  if(!id){ lErr('lid','Enter your Voter ID or email.'); ok=false; }
  if(!pw){ lErr('lpw','Enter your password.'); ok=false; }
  if(!ok) return;
  lSetBusy(true, true);
  setTimeout(function(){
    var user = getUsers().find(function(u){ return (u.id===id || u.email===id) && u.password===pw; });
    lSetBusy(true, false);
    if(!user){ lErr('lpw','Invalid credentials. Try voter/voter123'); toast('Login failed.'); return; }
    setCurUser(user);
    lSuccAnim('Welcome, '+user.name.split(' ')[0]+'! 🎉','Redirecting…');
    toast('Logged in ✓');
    setTimeout(function(){ goHome(); }, 2500);
  }, 900);
}
function lDoReg(){
  var first = document.getElementById('rfirst').value.trim();
  var last  = document.getElementById('rlast').value.trim();
  var email = document.getElementById('remail').value.trim();
  var bar   = document.getElementById('rbar').value;
  var pw    = document.getElementById('rpw').value;
  var conf  = document.getElementById('rconf').value;
  var ok = true;
  document.querySelectorAll('.linput').forEach(function(i){ i.classList.remove('err'); });
  document.querySelectorAll('.lerr').forEach(function(e){ e.classList.remove('show'); });
  if(!first){ lErr('rfirst','Required.'); ok=false; }
  if(!last){ lErr('rlast','Required.'); ok=false; }
  if(!email || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){ lErr('remail','Valid email required.'); ok=false; }
  if(!bar){ lErr('rbar','Select your barangay.'); ok=false; }
  if(pw.length < 8){ lErr('rpw','At least 8 characters.'); ok=false; }
  if(pw !== conf){ lErr('rconf','Passwords don\'t match.'); ok=false; }
  if(!ok) return;
  if(getUsers().find(function(u){ return u.email===email; })){ lErr('remail','Email already registered.'); return; }
  lSetBusy(false, true);
  setTimeout(function(){
    lSetBusy(false, false);
    var newId = 'V-'+Math.random().toString(36).substr(2,6).toUpperCase();
    var u = {id:newId, email:email, password:pw, name:first+' '+last, role:'voter', barangay:bar};
    var users = getUsers(); users.push(u); saveUsers(users);
    setCurUser(u);
    lSuccAnim('Account created! 🎉','Welcome, '+first+'!');
    toast('Voter ID: '+newId);
    setTimeout(function(){ goHome(); }, 2500);
  }, 1100);
}
// ── KEYBOARD NAVIGATION for sidebar items ──
document.addEventListener('keydown', function(e){
  if(e.key === 'Enter' && document.getElementById('loginPage').classList.contains('active')){
    if(lTab === 'login') lDoLogin(); else lDoReg();
  }
  // Allow Enter/Space to activate sidebar role=button items
  if((e.key === 'Enter' || e.key === ' ') && e.target.getAttribute('role') === 'button'){
    e.preventDefault();
    e.target.click();
  }
});

// ── HOME BALLOT LIST ──
var pillC = {live:'p-live', upcoming:'p-upcoming', closed:'p-closed'};
var pillL = {live:'● Live', upcoming:'Upcoming', closed:'Closed'};
var activeTag = 'all';
function makeBallotItem(e, i, hist){
  var voted = hist.find(function(h){ return h.eid===e.id; });
  var isPoll = e.type === 'poll';
  var d = document.createElement('div');
  d.className = 'bi';
  d.style.animationDelay = (0.03+i*0.04)+'s';
  d.innerHTML =
    '<div class="bico">'+e.icon+'</div>'+
    '<div class="binfo">'+
      '<div class="btitle">'+e.title+
        '<span class="'+(isPoll?'poll-tag':'election-tag')+'">'+(isPoll?'POLL':'ELECTION')+'</span>'+
        (voted?'<span style="font-size:15px;color:var(--subtle);margin-left:4px">✓ voted</span>':'')+
      '</div>'+
      '<div class="bdesc">'+e.desc+'</div>'+
    '</div>'+
    '<div class="bmeta">'+
      '<span class="btime">'+e.time+'</span>'+
      '<span class="bvotes"><div class="vbw"><div class="vb" style="width:'+e.pct+'%"></div></div>'+e.votes+'</span>'+
      '<span class="pill '+(pillC[e.status]||'p-closed')+'">'+(pillL[e.status]||e.status)+'</span>'+
    '</div>';
  d.addEventListener('click', function(){ goVoting(e); });
  return d;
}
function renderBlist(txt, tag){
  txt = txt || '';
  tag = tag || activeTag;
  var hist = getHistory();
  var filter = function(e){ return e.title.toLowerCase().includes(txt.toLowerCase()) && (tag==='all' || e.tag===tag); };
  var elEl = document.getElementById('blistElections');
  var poEl = document.getElementById('blistPolls');
  elEl.innerHTML = ''; poEl.innerHTML = '';
  var elections = allElectionsOnly().filter(filter);
  var polls = allPollsOnly().filter(filter);
  if(!elections.length) elEl.innerHTML = '<div class="empty-state" style="padding:12px 0;font-size:17px;color:#555;">No elections match.</div>';
  elections.forEach(function(e,i){ elEl.appendChild(makeBallotItem(e,i,hist)); });
  if(!polls.length) poEl.innerHTML = '<div class="empty-state" style="padding:12px 0;font-size:17px;color:#555;">No community polls yet. <a onclick="goAddPoll()">Create one →</a></div>';
  polls.forEach(function(e,i){ poEl.appendChild(makeBallotItem(e,i,hist)); });
}
function filterBallots(v){ renderBlist(v, activeTag); }
function chipF(el, tag){
  document.querySelectorAll('.chip').forEach(function(c){ c.classList.remove('active'); });
  el.classList.add('active');
  activeTag = tag;
  var searchVal = document.querySelector('.sinput') ? document.querySelector('.sinput').value : '';
  renderBlist(searchVal, tag);
}

// ── VOTING ──
var curEl = null, curPosIdx = 0, votes = {};
function renderPosSb(){
  var sb = document.getElementById('possb');
  sb.innerHTML = '<div class="possb-hd">Positions</div>';
  curEl.positions.forEach(function(pos, i){
    var d = document.createElement('div');
    d.className = 'posit' + (i===curPosIdx ? ' active' : '');
    d.innerHTML =
      '<div><div class="posit-name">'+pos.name+'</div><div class="posit-count">Pick '+pos.pick+'</div></div>'+
      '<span class="posit-check">'+(votes[i]!==undefined?'✓':'')+'</span>';
    (function(idx){ d.addEventListener('click', function(){ curPosIdx=idx; renderPosSb(); renderCands(); }); })(i);
    sb.appendChild(d);
  });
}
function renderCands(){
  var pos = curEl.positions[curPosIdx];
  document.getElementById('vcpos').textContent = pos.name;
  document.getElementById('vcins').textContent = 'Select '+pos.pick+' candidate'+(pos.pick>1?'s':'');
  document.getElementById('posnavinfo').textContent = 'Position '+(curPosIdx+1)+' of '+curEl.positions.length;
  var prevBtn = document.getElementById('prevBtn');
  prevBtn.disabled = curPosIdx===0;
  prevBtn.style.opacity = curPosIdx===0 ? '0.3' : '1';
  var isLast = curPosIdx===curEl.positions.length-1;
  document.getElementById('nextBtn').textContent = isLast ? 'Done ✓' : 'Next →';
  var grid = document.getElementById('cgrid');
  grid.innerHTML = '';
  var sh = ['#3A3A3A','#444','#333','#4A4A4A'];
  var totalVotes = pos.candidates.reduce(function(s,c){ return s+(c.votes||0); }, 0);
  var leading = pos.candidates.reduce(function(a,b){ return (a.votes||0)>(b.votes||0)?a:b; }, pos.candidates[0]);
  pos.candidates.forEach(function(c, ci){
    var card = document.createElement('div');
    card.className = 'ccard' + (votes[curPosIdx]===ci ? ' sel' : '');
    var pct = totalVotes > 0 ? Math.round(((c.votes||0)/totalVotes)*100) : 0;
    var isLeading = c===leading && totalVotes>0;
    var voteCount = c.votes!=null ? c.votes.toLocaleString() : '—';
    card.innerHTML =
      '<div class="cphoto">'+
        '<div class="cnum">#'+(ci+1)+'</div>'+
        '<div class="cphoto-inner">👤</div>'+
        '<div class="cbar" style="background:'+sh[ci%4]+'"></div>'+
        (isLeading?'<div style="position:absolute;top:10px;right:10px;font-family:\'Press Start 2P\',monospace;font-size:7px;color:var(--ut-yellow);border:2px solid var(--ut-yellow);padding:2px 5px;background:#000;">LEADING</div>':'')+
      '</div>'+
      '<div class="cinfo">'+
        '<div class="cname">'+c.name+'</div>'+
        '<div class="cparty">'+c.party+'</div>'+
        '<div class="ctags">'+(c.tags||[]).map(function(t){ return '<span class="ctag">'+t+'</span>'; }).join('')+'</div>'+
      '</div>'+
      '<div class="cand-vote-stats">'+
        '<div class="cand-vote-label"><span>'+voteCount+' votes</span><span class="cand-vote-pct">'+pct+'%</span></div>'+
        '<div class="cand-vote-bar-wrap"><div class="cand-vote-bar" style="width:'+pct+'%;background:'+(isLeading?'var(--ut-yellow)':'var(--white)')+'"></div></div>'+
      '</div>';
    (function(idx){ card.addEventListener('click', function(){ votes[curPosIdx]=idx; renderCands(); renderPosSb(); updCounter(); }); })(ci);
    grid.appendChild(card);
  });
}
function updCounter(){
  var total = curEl.positions.length;
  var filled = Object.keys(votes).length;
  document.getElementById('vcounter').textContent = filled+' / '+total+' filled';
  document.getElementById('vsubmit').classList.toggle('ready', filled===total);
}
function changePosIdx(dir){
  var ni = curPosIdx + dir;
  if(ni < 0) return;
  if(ni >= curEl.positions.length){ toast('All positions navigated! Submit when ready.'); return; }
  curPosIdx = ni; renderPosSb(); renderCands();
}
function openModal(){
  var sum = document.getElementById('msum');
  sum.innerHTML = '';
  curEl.positions.forEach(function(pos, i){
    var c = pos.candidates[votes[i]];
    var r = document.createElement('div');
    r.className = 'mrow';
    r.innerHTML = '<span class="mpos">'+pos.name+'</span><span class="mcand">'+(c?c.name:'—')+'</span>';
    sum.appendChild(r);
  });
  document.getElementById('modalVote').classList.add('show');
}
function closeModal(id){ document.getElementById(id).classList.remove('show'); }
function doSubmit(){
  closeModal('modalVote');
  var u = getCurUser();
  var entry = {
    eid: curEl.id, title: curEl.title, icon: curEl.icon,
    date: new Date().toLocaleDateString('en-PH',{year:'numeric',month:'long',day:'numeric'}),
    selections: curEl.positions.map(function(pos,i){ return {pos:pos.name, cand:(pos.candidates[votes[i]]?pos.candidates[votes[i]].name:'—')}; }),
    hash: 'EVOTE-'+Math.random().toString(36).substr(2,8).toUpperCase()+'-'+Date.now().toString(36).toUpperCase()
  };
  addHistory(entry);
  votes = {};
  toast('✓ Vote submitted successfully!');
  setTimeout(function(){ goHome(); }, 1000);
}

// ── RESULTS ──
var curResFilter = 'all';
var curResElection = null;
function renderResults(){
  var scroll = document.getElementById('resultsScroll');
  if(curResElection){ renderElectionResults(curResElection); return; }
  scroll.innerHTML = '';
  var tabBar = document.createElement('div');
  tabBar.className = 'res-filter-tabs';
  [['all','All'],['live','Live'],['closed','Closed'],['upcoming','Upcoming']].forEach(function(pair){
    var t = document.createElement('div');
    t.className = 'res-tab'+(curResFilter===pair[0]?' active':'');
    t.textContent = pair[1];
    t.onclick = function(){ curResFilter=pair[0]; renderResults(); };
    tabBar.appendChild(t);
  });
  scroll.appendChild(tabBar);
  var hdr = document.createElement('div');
  hdr.className = 'page-header';
  hdr.innerHTML = '<h2>Election Results</h2><p>Live and final results. Click any to see full breakdown.</p>';
  scroll.appendChild(hdr);
  var all = allBallots().filter(function(e){ return e.positions && e.positions.length>0; });
  var filtered = all.filter(function(e){ return curResFilter==='all' || e.status===curResFilter; });
  if(!filtered.length){ scroll.innerHTML += '<div class="empty-state">No elections found for this filter.</div>'; return; }
  filtered.forEach(function(el, i){
    var totalVotes = 0;
    var winners = [];
    el.positions.forEach(function(pos){
      var tv = pos.candidates.reduce(function(s,c){ return s+(c.votes||0); }, 0);
      totalVotes += tv;
      if(pos.candidates.length){
        var w = pos.candidates.reduce(function(a,b){ return (a.votes||0)>(b.votes||0)?a:b; });
        winners.push({pos:pos.name, cand:w.name, votes:w.votes||0});
      }
    });
    var statusCls = el.status==='live'?'live':el.status==='closed'?'closed':'upcoming';
    var statusLabel = el.status==='live'?'● LIVE':el.status==='closed'?'CLOSED':'UPCOMING';
    var winnerPreview = winners.slice(0,2).map(function(w){
      return '<span style="color:#aaa;font-size:16px;">'+w.pos+': <strong style="color:#fff">'+w.cand+'</strong></span>';
    }).join(' · ');
    var item = document.createElement('div');
    item.className = 'res-list-item';
    item.style.animationDelay = (i*0.04)+'s';
    item.innerHTML =
      '<div class="res-list-icon">'+el.icon+'</div>'+
      '<div style="flex:1;min-width:0;">'+
        '<div style="font-family:\'Press Start 2P\',monospace;font-size:10px;color:#fff;margin-bottom:4px;">'+el.title+'</div>'+
        '<div style="font-size:16px;color:var(--muted);margin-bottom:6px;">'+(el.desc||'')+' · '+el.positions.length+' position'+(el.positions.length!==1?'s':'')+' · '+totalVotes.toLocaleString()+' total votes</div>'+
        '<div style="display:flex;gap:10px;flex-wrap:wrap;">'+winnerPreview+'</div>'+
      '</div>'+
      '<div style="flex-shrink:0;display:flex;flex-direction:column;align-items:flex-end;gap:6px;">'+
        '<span class="res-list-status '+statusCls+'">'+statusLabel+'</span>'+
        '<span style="font-family:\'VT323\',monospace;font-size:17px;color:var(--muted);">'+(el.votes||'0')+' voters</span>'+
      '</div>';
    (function(e){ item.addEventListener('click', function(){ curResElection=e; renderElectionResults(e); }); })(el);
    scroll.appendChild(item);
  });
}
function renderElectionResults(el){
  var scroll = document.getElementById('resultsScroll');
  scroll.innerHTML = '';
  var backRow = document.createElement('div');
  backRow.className = 'res-header';
  var statusCls2 = el.status==='live'?'live':el.status==='closed'?'closed':'upcoming';
  var statusLabel2 = el.status==='live'?'● LIVE':el.status==='closed'?'CLOSED':'UPCOMING';
  backRow.innerHTML =
    '<button class="res-back" onclick="curResElection=null;renderResults();">← All Results</button>'+
    '<div><div class="res-election-title">'+el.icon+' '+el.title+'</div><div class="res-election-meta">'+(el.desc||'')+' · '+el.time+'</div></div>'+
    '<div style="margin-left:auto;"><span class="res-list-status '+statusCls2+'" style="font-family:\'Press Start 2P\',monospace;font-size:8px;padding:4px 10px;border:2px solid;display:inline-block;">'+statusLabel2+'</span></div>';
  scroll.appendChild(backRow);
  var allCandVotes = [];
  el.positions.forEach(function(p){ p.candidates.forEach(function(c){ allCandVotes.push(c.votes||0); }); });
  var totalVotes = allCandVotes.reduce(function(s,v){ return s+v; }, 0);
  var totalReg = parseInt((el.votes||'0').replace(/[^0-9]/g,''))||totalVotes||1;
  var turnout = totalReg>0 ? Math.min(100,Math.round((totalVotes/totalReg)*100)) : 0;
  var statRow = document.createElement('div');
  statRow.className = 'res-stats-row';
  statRow.innerHTML =
    '<div class="res-stat-card"><div class="res-stat-val">'+totalVotes.toLocaleString()+'</div><div class="res-stat-label">Total Votes Cast</div></div>'+
    '<div class="res-stat-card"><div class="res-stat-val">'+el.positions.length+'</div><div class="res-stat-label">Positions</div></div>'+
    '<div class="res-stat-card"><div class="res-stat-val" style="color:var(--ut-yellow);">'+turnout+'%</div><div class="res-stat-label">Turnout</div><div class="res-turnout-bar"><div class="res-turnout-fill" style="width:0%" data-target="'+turnout+'"></div></div></div>';
  scroll.appendChild(statRow);
  el.positions.forEach(function(pos, pi){
    var posTotal = pos.candidates.reduce(function(s,c){ return s+(c.votes||0); }, 0);
    var sorted = pos.candidates.slice().sort(function(a,b){ return (b.votes||0)-(a.votes||0); });
    var winner = sorted[0];
    var block = document.createElement('div');
    block.className = 'res-pos-block';
    block.style.animationDelay = (pi*0.06)+'s';
    var candsHtml = '<div class="res-cands">';
    sorted.forEach(function(c, rank){
      var pct = posTotal>0 ? ((c.votes||0)/posTotal*100).toFixed(1) : '0.0';
      var isFirst = rank===0 && posTotal>0;
      var isSecond = rank===1;
      var barClass = isFirst?'first':isSecond?'second':'other';
      candsHtml +=
        '<div class="res-cand-row'+(isFirst?' winner':'')+'">'+
          (isFirst?'<div class="res-winner-crown">👑</div>':'')+
          '<div class="res-cand-rank'+(isFirst?' gold':'')+'">#'+(rank+1)+'</div>'+
          '<div class="res-cand-info"><div class="res-cand-name">'+c.name+'</div><div class="res-cand-party">'+(c.party||'—')+'</div>'+
            '<div class="res-cand-bar-wrap"><div class="res-cand-bar '+barClass+'" style="width:0%" data-target="'+pct+'%"></div></div>'+
          '</div>'+
          '<div class="res-cand-votes"><span class="res-pct-badge '+(isFirst?'first-b':'other-b')+'">'+pct+'%</span><div class="res-total-label">'+((c.votes||0).toLocaleString())+' votes</div></div>'+
        '</div>';
    });
    candsHtml += '</div>';
    block.innerHTML =
      '<div class="res-pos-header"><div><div class="res-pos-name">'+pos.name+'</div><div style="font-size:16px;color:var(--muted);margin-top:3px;">'+posTotal.toLocaleString()+' votes cast · Pick '+pos.pick+'</div></div>'+
      (winner&&posTotal>0?'<div style="text-align:right;"><div class="res-winner-label">CURRENT LEADER</div><div style="font-family:\'VT323\',monospace;font-size:20px;color:#fff;">'+winner.name+'</div></div>':'')+'</div>'+candsHtml;
    scroll.appendChild(block);
  });
  requestAnimationFrame(function(){
    setTimeout(function(){
      scroll.querySelectorAll('[data-target]').forEach(function(el){
        el.style.transition = 'width .8s cubic-bezier(.4,0,.2,1)';
        el.style.width = el.dataset.target;
      });
    }, 80);
  });
}

// ── PROFILE ──
function renderProfile(){
  var u = getCurUser(); if(!u) return;
  var hist = getHistory(); var polls = getUserPolls();
  var ini = u.name.split(' ').map(function(w){ return w[0]; }).slice(0,2).join('');
  document.getElementById('profAv').textContent = ini;
  document.getElementById('profName').textContent = u.name;
  document.getElementById('profId').textContent = 'Voter ID: '+u.id+'  ·  '+u.email;
  document.getElementById('profBadges').innerHTML =
    '<span class="profile-badge verified">✓ Verified</span>'+
    '<span class="profile-badge">'+(u.barangay||'—')+'</span>'+
    '<span class="profile-badge">'+(u.role==='admin'?'Administrator':'Citizen')+'</span>';
  var liveHasVote = allElections().filter(function(e){ return e.status==='live'&&e.positions&&e.positions.length; });
  var votedIds = {};
  hist.forEach(function(h){ votedIds[h.eid]=true; });
  document.getElementById('profVoted').textContent = hist.length;
  document.getElementById('profPending').textContent = Math.max(0, liveHasVote.length-Object.keys(votedIds).length);
  document.getElementById('profCreated').textContent = polls.length;
  var vhl = document.getElementById('vHistList');
  vhl.innerHTML = '';
  if(!hist.length){
    vhl.innerHTML = '<div class="empty-state">No votes cast yet. <a onclick="goHome()">Browse elections →</a></div>';
  } else {
    hist.forEach(function(h, i){
      var d = document.createElement('div');
      d.className = 'vhist-item';
      d.style.animationDelay = (i*0.04)+'s';
      d.innerHTML =
        '<div class="vhist-icon">'+(h.icon||'🗳')+'</div>'+
        '<div class="vhist-info"><div class="vhist-title">'+h.title+'</div><div class="vhist-sub">'+(h.selections?h.selections.length:0)+' positions · '+(h.selections?h.selections.map(function(s){ return s.cand; }).join(', '):'—')+'</div></div>'+
        '<div class="vhist-meta"><div class="vhist-date">'+h.date+'</div><button class="cert-btn" onclick="showCert('+i+')">📄 Certificate</button></div>';
      vhl.appendChild(d);
    });
  }
  var cpl = document.getElementById('createdList');
  cpl.innerHTML = '';
  if(!polls.length){
    cpl.innerHTML = '<div class="empty-state">No polls created yet. <a onclick="goAddPoll()">Create one →</a></div>';
  } else {
    polls.forEach(function(p, i){
      var d = document.createElement('div');
      d.className = 'vhist-item';
      d.style.animationDelay = (i*0.04)+'s';
      d.innerHTML =
        '<div class="vhist-icon">'+(p.icon||'📋')+'</div>'+
        '<div class="vhist-info"><div class="vhist-title">'+p.title+'</div><div class="vhist-sub">'+(p.positions?p.positions.length:0)+' positions · '+(p.tag||'general')+'</div></div>'+
        '<div class="vhist-meta"><div class="vhist-date">'+(p.createdDate||'—')+'</div><span class="pill p-'+(p.status==='live'?'live':p.status==='upcoming'?'upcoming':'closed')+'">'+(p.status||'draft')+'</span></div>';
      cpl.appendChild(d);
    });
  }
}
function showCert(idx){
  var h = getHistory()[idx]; var u = getCurUser(); if(!h||!u) return;
  document.getElementById('certContent').innerHTML =
    '<div style="font-family:\'Press Start 2P\',monospace;font-weight:700;font-size:11px;margin-bottom:12px;">🗳 Official Vote Certificate</div>'+
    '<div><strong>Voter:</strong> '+u.name+'</div>'+
    '<div><strong>Voter ID:</strong> '+u.id+'</div>'+
    '<div><strong>Election:</strong> '+h.title+'</div>'+
    '<div><strong>Date Voted:</strong> '+h.date+'</div>'+
    '<div style="margin-top:10px;padding-top:10px;border-top:1px solid var(--rule)"><strong>Selections:</strong></div>'+
    (h.selections||[]).map(function(s){ return '<div style="margin-top:4px">• '+s.pos+': <strong>'+s.cand+'</strong></div>'; }).join('')+
    '<div class="cert-hash">Verification Hash: '+h.hash+'</div>';
  document.getElementById('modalCert').classList.add('show');
}

// ── SETTINGS ──
function toggleSetting(el){
  el.classList.toggle('on');
  var s = getSettings(); s[el.id] = el.classList.contains('on'); saveSettings(s);
  toast(el.classList.contains('on') ? 'Setting enabled ✓' : 'Setting disabled');
}
var editField = '';
function openEdit(field, label){
  editField = field;
  var u = getCurUser();
  document.getElementById('editTitle').textContent = 'Edit '+label;
  document.getElementById('editSub').textContent = 'Update your '+label.toLowerCase();
  document.getElementById('editInput').value = u ? (u[field]||'') : '';
  document.getElementById('modalEdit').classList.add('show');
}
function saveEdit(){
  var val = document.getElementById('editInput').value.trim();
  if(!val){ toast('Field cannot be empty.'); return; }
  var u = getCurUser(); if(!u) return;
  u[editField] = val;
  setCurUser(u);
  var users = getUsers();
  var idx = users.findIndex(function(x){ return x.id===u.id; });
  if(idx >= 0){ users[idx] = u; saveUsers(users); }
  var map = {name:'sName', email:'sEmail', barangay:'sBarangay'};
  if(map[editField]) document.getElementById(map[editField]).textContent = val;
  closeModal('modalEdit');
  toast(editField+' updated ✓');
}
function exportData(){
  var data = {user:getCurUser(), voteHistory:getHistory(), createdPolls:getUserPolls(), settings:getSettings()};
  var blob = new Blob([JSON.stringify(data,null,2)], {type:'application/json'});
  var a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = 'skibivote_data.json';
  a.click();
  toast('Data exported ✓');
}

// ── CATEGORIES ──
function renderCategories(){
  var followed = getFollowed();
  var grid = document.getElementById('catGrid');
  grid.innerHTML = '';
  CATEGORIES.forEach(function(cat, i){
    var f = followed.indexOf(cat.id) >= 0;
    var d = document.createElement('div');
    d.className = 'cat-card'+(f?' followed':'');
    d.style.animationDelay = (i*0.05)+'s';
    d.innerHTML =
      '<div class="cat-check">'+(f?'✓':'')+'</div>'+
      '<div class="cat-icon">'+cat.icon+'</div>'+
      '<div class="cat-name">'+cat.name+'</div>'+
      '<div class="cat-count">'+cat.count+' elections</div>'+
      '<div class="cat-desc">'+cat.desc+'</div>';
    (function(c){
      d.addEventListener('click', function(){
        var f2 = getFollowed();
        var idx2 = f2.indexOf(c.id);
        if(idx2>=0) f2.splice(idx2,1); else f2.push(c.id);
        saveFollowed(f2);
        toast(f2.indexOf(c.id)>=0 ? 'Following '+c.name+' ✓' : 'Unfollowed '+c.name);
        renderCategories();
      });
    })(cat);
    grid.appendChild(d);
  });
  var bl = document.getElementById('catBlist');
  bl.innerHTML = '';
  var f2 = getFollowed();
  var filtered = allElections().filter(function(e){ return f2.indexOf(e.tag)>=0; });
  if(!filtered.length){ bl.innerHTML = '<div class="empty-state">No elections in followed categories.</div>'; }
  filtered.forEach(function(e, i){
    var d = document.createElement('div');
    d.className = 'bi';
    d.style.animationDelay = (i*0.04)+'s';
    d.innerHTML =
      '<div class="bico">'+e.icon+'</div>'+
      '<div class="binfo"><div class="btitle">'+e.title+'</div><div class="bdesc">'+e.desc+'</div></div>'+
      '<div class="bmeta"><span class="btime">'+e.time+'</span><span class="pill '+(pillC[e.status]||'p-closed')+'">'+(pillL[e.status]||e.status)+'</span></div>';
    (function(el){ d.addEventListener('click', function(){ goVoting(el); }); })(e);
    bl.appendChild(d);
  });
}

// ── POSITION PRESETS ──
function onCatChange(){
  var cat = document.getElementById('pollCat').value;
  var panel = document.getElementById('presetPanel');
  if(cat && POSITION_PRESETS[cat]){ panel.style.display = 'block'; buildPresetPanel(cat); }
  else { panel.style.display = 'none'; }
  updatePreview();
}
function togglePresetPanel(){
  var body = document.getElementById('presetBody');
  var arrow = document.getElementById('presetArrow');
  body.classList.toggle('open');
  arrow.textContent = body.classList.contains('open') ? '▲' : '▼';
}
function buildPresetPanel(cat){
  var body = document.getElementById('presetBody');
  body.innerHTML = '';
  body.classList.add('open');
  document.getElementById('presetArrow').textContent = '▲';
  var preset = POSITION_PRESETS[cat];
  if(!preset) return;
  var group = document.createElement('div');
  group.className = 'pos-preset-group';
  group.innerHTML = '<div class="pos-preset-group-label">'+preset.label+' — click to add position</div>';
  var items = document.createElement('div');
  items.className = 'pos-preset-items';
  preset.positions.forEach(function(posName){
    var btn = document.createElement('div');
    btn.className = 'pos-preset-item';
    btn.id = 'preset_'+posName.replace(/[^a-z0-9]/gi,'_');
    btn.textContent = '+ '+posName;
    (function(name, b){ btn.onclick = function(){ addPresetPosition(name, b); }; })(posName, btn);
    items.appendChild(btn);
  });
  group.appendChild(items);
  body.appendChild(group);
  var cg = document.createElement('div');
  cg.className = 'pos-preset-group';
  cg.style.marginTop = '10px';
  cg.innerHTML = '<div class="pos-preset-group-label">Or add your own below ↓</div>';
  body.appendChild(cg);
}
function addPresetPosition(posName, btn){
  if(btn.classList.contains('used')){ toast('Position already added!'); return; }
  btn.classList.add('used'); btn.textContent = '✓ '+posName;
  addPos(posName); toast('Added: '+posName);
}
var posCount = 0;
function addPos(presetName){
  presetName = presetName || '';
  posCount++;
  var id = 'pos_'+posCount;
  var c = document.getElementById('posContainer');
  var div = document.createElement('div');
  div.className = 'pos-builder'; div.id = id;
  div.innerHTML =
    '<div class="pos-hdr">'+
      '<input type="text" class="pos-title-inp" placeholder="Position name (e.g. President)" value="'+presetName+'" oninput="updatePreview();syncPresetUsed()">'+
      '<button class="pos-rm" onclick="onRemovePos(\''+id+'\',\''+presetName.replace(/'/g,"\\'")+'\')" style="background:transparent;border:none;color:var(--muted);font-size:18px;cursor:pointer;padding:4px;">✕</button>'+
    '</div>'+
    '<div class="cands-list" id="cl_'+id+'">'+
      '<div class="cand-row"><input type="text" class="cand-inp" placeholder="Candidate 1" oninput="updatePreview()"><button class="cand-rm" onclick="this.parentElement.remove();updatePreview()" style="background:transparent;border:none;color:var(--muted);font-size:16px;cursor:pointer;">✕</button></div>'+
      '<div class="cand-row"><input type="text" class="cand-inp" placeholder="Candidate 2" oninput="updatePreview()"><button class="cand-rm" onclick="this.parentElement.remove();updatePreview()" style="background:transparent;border:none;color:var(--muted);font-size:16px;cursor:pointer;">✕</button></div>'+
    '</div>'+
    '<button class="add-cand-btn" onclick="addCand(\'cl_'+id+'\')">+ Add Candidate</button>';
  c.appendChild(div); updatePreview();
}
function onRemovePos(divId, presetName){
  var el2 = document.getElementById(divId);
  if(el2) el2.remove();
  updatePreview();
  if(presetName){
    var btnId = 'preset_'+presetName.replace(/[^a-z0-9]/gi,'_');
    var btn = document.getElementById(btnId);
    if(btn){ btn.classList.remove('used'); btn.textContent='+ '+presetName; }
  }
}
function syncPresetUsed(){
  var added = Array.from(document.querySelectorAll('.pos-title-inp')).map(function(i){ return i.value.trim(); }).filter(Boolean);
  document.querySelectorAll('.pos-preset-item').forEach(function(btn){
    var name = btn.textContent.replace(/^[+✓] /,'');
    if(added.indexOf(name)>=0){ btn.classList.add('used'); btn.textContent='✓ '+name; }
    else{ btn.classList.remove('used'); btn.textContent='+ '+name; }
  });
}
function addCand(cid){
  var c = document.getElementById(cid);
  var n = c.children.length+1;
  var r = document.createElement('div');
  r.className = 'cand-row';
  r.innerHTML = '<input type="text" class="cand-inp" placeholder="Candidate '+n+'" oninput="updatePreview()"><button class="cand-rm" onclick="this.parentElement.remove();updatePreview()" style="background:transparent;border:none;color:var(--muted);font-size:16px;cursor:pointer;">✕</button>';
  c.appendChild(r); updatePreview();
}
function updatePreview(){
  var title = (document.getElementById('pollTitle')||{}).value || 'Untitled Poll';
  var positions = Array.from(document.querySelectorAll('.pos-builder')).map(function(pb){
    return { name: (pb.querySelector('.pos-title-inp')||{}).value || 'Position', cands: Array.from(pb.querySelectorAll('.cand-inp')).map(function(i){ return i.value; }).filter(Boolean) };
  });
  var pb = document.getElementById('pollPreviewBody');
  pb.innerHTML =
    '<div style="font-family:\'Press Start 2P\',monospace;font-weight:700;font-size:10px;margin-bottom:10px;">'+title+'</div>'+
    positions.map(function(p){
      return '<div class="preview-item"><div class="preview-pos">'+p.name+'</div><div class="preview-cands">'+(p.cands.length?p.cands.join(', '):'No candidates yet')+'</div></div>';
    }).join('')+
    (!positions.length?'<div style="color:var(--muted);font-size:17px">Add a position below…</div>':'');
}
function submitPoll(mode){
  var title = (document.getElementById('pollTitle').value||'').trim();
  var cat = document.getElementById('pollCat').value;
  var type = document.getElementById('pollType').value || 'poll';
  if(!title){ toast('Please enter a poll title.'); return; }
  if(!cat && mode==='live'){ toast('Please select a category.'); return; }
  var icons = {national:'🏛',local:'🏙',barangay:'🏘',school:'🎓',org:'🏢',survey:'📊'};
  var positions = Array.from(document.querySelectorAll('.pos-builder')).map(function(pb){
    var name = (pb.querySelector('.pos-title-inp')||{}).value || 'Position';
    var candidates = Array.from(pb.querySelectorAll('.cand-inp')).map(function(i){ return i.value.trim(); }).filter(Boolean).map(function(n){ return {name:n,party:'Independent',tags:[],votes:0}; });
    return {name:name, pick:1, candidates:candidates};
  });
  var poll = {
    id: 'poll_'+Date.now(), icon: icons[cat]||'📋', title: title, type: type,
    desc: document.getElementById('pollDesc').value || 'No description',
    time: 'Just now', votes: '0', pct: 0, status: mode==='draft'?'upcoming':'live',
    tag: cat||'org', createdBy: getCurUser() ? getCurUser().id : 'anon',
    createdDate: new Date().toLocaleDateString('en-PH',{year:'numeric',month:'short',day:'numeric'}), positions: positions
  };
  var polls = getUserPolls(); polls.unshift(poll); saveUserPolls(polls);
  toast(mode==='draft' ? 'Draft saved! 💾' : 'Poll published! 🎉');
  document.getElementById('pollTitle').value = '';
  document.getElementById('pollDesc').value = '';
  document.getElementById('pollCat').value = '';
  document.getElementById('posContainer').innerHTML = '';
  document.getElementById('presetPanel').style.display = 'none';
  posCount = 0; updatePreview();
  setTimeout(function(){ goHome(); }, 900);
}

// ── CONTACT ──
function updateCharCount(){
  var msg = document.getElementById('cMsg').value;
  var el = document.getElementById('cCharCount');
  el.textContent = msg.length + ' / 800';
  el.className = 'char-count' + (msg.length > 750 ? ' warn' : '') + (msg.length >= 800 ? ' over' : '');
}
function submitContact(){
  var name = document.getElementById('cName').value.trim();
  var email = document.getElementById('cEmail').value.trim();
  var subject = document.getElementById('cSubject').value;
  var msg = document.getElementById('cMsg').value.trim();
  if(!name){ toast('Please enter your name.'); return; }
  if(!email || !email.includes('@')){ toast('Please enter a valid email.'); return; }
  if(!subject){ toast('Please select a subject.'); return; }
  if(msg.length < 10){ toast('Message is too short.'); return; }
  var btn = document.getElementById('cSubmitBtn');
  btn.disabled = true;
  btn.textContent = '[ SENDING... ]';
  setTimeout(function(){
    document.getElementById('contactFormArea').style.display = 'none';
    document.getElementById('contactSuccess').classList.add('show');
  }, 800);
}
function resetContact(){
  document.getElementById('contactFormArea').style.display = 'block';
  document.getElementById('contactSuccess').classList.remove('show');
  document.getElementById('cName').value = '';
  document.getElementById('cEmail').value = '';
  document.getElementById('cSubject').value = '';
  document.getElementById('cMsg').value = '';
  document.getElementById('cCharCount').textContent = '0 / 800';
  var btn = document.getElementById('cSubmitBtn');
  btn.disabled = false; btn.textContent = '[ SEND MESSAGE ]';
}

// ── TESTIMONIALS ──
var testiData = [
  {name:'Reyna Santos',initials:'RS',role:'organizer',tag:'organizer',rating:5,text:'Our barangay election was handled flawlessly. Candidates were entered in minutes, live results came in instantly. The community trusted the process because everything was transparent.',org:'Brgy. Mabini',likes:84},
  {name:'Mark Flores',initials:'MF',role:'voter',tag:'voter',rating:5,text:'Super convenient! I voted from my phone in under 2 minutes. No long lines, no confusing paper forms. This is how elections should be.',org:'Pasig City',likes:62},
  {name:'Aileen Ramos',initials:'AR',role:'student',tag:'student',rating:5,text:'Our org used this for SSG elections and it was a total vibe. The retro pixel design had everyone posting screenshots. Voter participation was the highest ever.',org:'DLSU Manila',likes:57},
  {name:'Joshua Tan',initials:'JT',role:'admin',tag:'admin',rating:5,text:'The poll builder is incredibly flexible. We ran a multi-position election with 30+ candidates and the system never lagged. Results exported cleanly too.',org:'Private Company',likes:41},
  {name:'Liza Mercado',initials:'LM',role:'voter',tag:'voter',rating:4,text:'Great experience overall. Wish there was an app version but the mobile site works well. Results page is very satisfying to watch update in real time.',org:'Quezon City',likes:38},
  {name:'Bong Castillo',initials:'BC',role:'organizer',tag:'organizer',rating:5,text:'Set up a community poll in 10 minutes. Shared the link and got 200+ responses overnight. The category tags help people find relevant elections easily.',org:'Makati',likes:33},
  {name:'Trisha Villanueva',initials:'TV',role:'student',tag:'student',rating:5,text:'SkibiVote gave our USC the legitimacy it needed. Digital voting records, transparent counts — no more drama about paper vote tampering.',org:'Ateneo de Manila',likes:29},
  {name:'Paolo Reyes',initials:'PR',role:'voter',tag:'voter',rating:5,text:'Voted in my first election ever through this. The UI is so intuitive that I never needed instructions. Felt proud to participate.',org:'Muntinlupa',likes:22},
  {name:'Grace Ocampo',initials:'GO',role:'organizer',tag:'organizer',rating:4,text:'Works brilliantly for school elections. Only feedback is a reminder notification feature would push turnout even higher. But overall, excellent platform.',org:'St. Scholastica',likes:17},
  {name:'Dom Aquino',initials:'DA',role:'admin',tag:'admin',rating:5,text:'The backend is reliable and fast. We\'ve processed over 5,000 votes in a single session with zero downtime. Extremely impressed.',org:'Tech Team',likes:45},
];
var testiFilterCurrent = 'all';
var testiVisible = 6;

function renderTestimonials(){
  var grid = document.getElementById('testiGrid');
  var filtered = testiFilterCurrent === 'all' ? testiData : (testiFilterCurrent === '5' ? testiData.filter(function(t){return t.rating===5;}) : testiData.filter(function(t){return t.role===testiFilterCurrent;}));
  grid.innerHTML = '';
  filtered.slice(0, testiVisible).forEach(function(t, i){
    var stars = '';
    for(var s=1;s<=5;s++) stars += '<span class="testi-star'+(s<=t.rating?'':' empty')+'">★</span>';
    var card = document.createElement('div');
    card.className = 'testi-card';
    card.style.animationDelay = (i*0.05)+'s';
    card.innerHTML =
      '<div class="testi-quote">"'+t.text+'"</div>'+
      '<div class="testi-footer">'+
        '<div class="testi-av">'+t.initials+'</div>'+
        '<div>'+
          '<div class="testi-name">'+t.name+(t.rating===5?' <span style="color:var(--ut-yellow);font-size:12px">✓</span>':'')+'</div>'+
          '<div class="testi-meta">'+t.org+'</div>'+
          '<div class="testi-stars">'+stars+'</div>'+
        '</div>'+
        '<span class="testi-tag '+t.tag+'">'+t.tag.toUpperCase()+'</span>'+
      '</div>'+
      '<div style="margin-top:10px;border-top:2px solid #1a1a1a;padding-top:9px;display:flex;justify-content:flex-end;">'+
        '<button class="like-btn" data-idx="'+testiData.indexOf(t)+'">♥ '+t.likes+'</button>'+
      '</div>';
    grid.appendChild(card);
  });
  grid.querySelectorAll('.like-btn').forEach(function(btn){
    btn.addEventListener('click', function(){
      if(btn.classList.contains('liked')) return;
      btn.classList.add('liked');
      var idx = parseInt(btn.dataset.idx);
      testiData[idx].likes++;
      btn.textContent = '♥ '+testiData[idx].likes;
    });
  });
  document.getElementById('testiLoadMoreBtn').style.display = filtered.length > testiVisible ? 'block' : 'none';
}
function testiFilter(el, type){
  document.querySelectorAll('.testi-filter-bar .chip').forEach(function(c){c.classList.remove('active');});
  el.classList.add('active');
  testiFilterCurrent = type;
  testiVisible = 6;
  renderTestimonials();
}
function testiLoadMore(){
  testiVisible += 4;
  renderTestimonials();
}

var selectedStars = 0;
function setStars(n){
  selectedStars = n;
  document.querySelectorAll('.star-pick').forEach(function(s,i){ s.classList.toggle('on', i < n); });
}
function openWriteModal(){ document.getElementById('modalReview').classList.add('show'); }
function submitReview(){
  var name = document.getElementById('rName').value.trim();
  var role = document.getElementById('rRole').value;
  var text = document.getElementById('rText').value.trim();
  if(!name){ toast('Please enter your name.'); return; }
  if(!selectedStars){ toast('Please select a rating.'); return; }
  if(text.length < 20){ toast('Review must be at least 20 characters.'); return; }
  var initials = name.split(' ').map(function(w){return w[0];}).join('').slice(0,2).toUpperCase();
  testiData.unshift({name:name,initials:initials,role:role,tag:role,rating:selectedStars,text:text,org:'SkibiVote User',likes:0});
  closeModal('modalReview');
  document.getElementById('rName').value = '';
  document.getElementById('rText').value = '';
  document.getElementById('rRole').value = 'voter';
  setStars(0); selectedStars = 0;
  testiVisible = 6; testiFilterCurrent = 'all';
  document.querySelectorAll('.testi-filter-bar .chip').forEach(function(c,i){c.classList.toggle('active',i===0);});
  renderTestimonials();
  toast('Review submitted! ❤');
}

// ── CHAT WIDGET ──
var chatHistory = [];
var chatLoading = false;
var chatOpen = false;

var CHAT_SYSTEM = "You are SkibiVote Support Bot — a helpful, friendly assistant for SkibiVote, a retro pixel-art themed online voting platform popular in the Philippines. SkibiVote allows users to create elections, polls, and votes for schools, barangays, organizations, and national contexts. Keep answers short and helpful (2-4 sentences max unless the user needs detailed steps). Use casual, friendly language. You know the platform has: election creation with multiple positions and candidates, live results, categories (national, local, barangay, school, org, survey), voting history, profiles, certificates, and a settings page. If you don't know something specific about SkibiVote, give general helpful guidance. Do not use markdown headers or bullet points — write in plain conversational sentences.";

function toggleChat(){
  chatOpen = !chatOpen;
  document.getElementById('chatWindow').classList.toggle('hidden', !chatOpen);
  if(chatOpen){
    document.getElementById('chatFabBadge').style.display = 'none';
    if(chatHistory.length === 0) chatAddMsg('bot', "Hey! 👋 Welcome to SkibiVote Support. I\'m your AI assistant — ask me anything about voting, creating elections, results, or account help.");
    chatScrollBottom();
  }
}
function closeChat(){
  chatOpen = false;
  document.getElementById('chatWindow').classList.add('hidden');
}
function chatAddMsg(role, text, id){
  var msgs = document.getElementById('chatMsgs');
  var div = document.createElement('div');
  div.className = 'chat-msg '+role;
  if(id) div.id = id;
  var now = new Date();
  var time = now.getHours()+':'+(now.getMinutes()<10?'0':'')+now.getMinutes();
  if(role==='bot' && text==='__typing__'){
    div.innerHTML = '<div class="chat-bubble"><div class="chat-typing"><div class="chat-dot"></div><div class="chat-dot"></div><div class="chat-dot"></div></div></div>';
  } else {
    div.innerHTML = '<div class="chat-bubble">'+chatEsc(text)+'</div><div class="chat-time">'+time+'</div>';
  }
  msgs.appendChild(div);
  chatScrollBottom();
  return div;
}
function chatEsc(t){ return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }
function chatScrollBottom(){ var m=document.getElementById('chatMsgs'); m.scrollTop=m.scrollHeight; }
async function chatSend(){
  var inp = document.getElementById('chatInputEl');
  var text = inp.value.trim();
  if(!text || chatLoading) return;
  inp.value = ''; inp.style.height = '';
  await chatSendText(text);
}
function chatQuick(text){
  document.getElementById('chatQR').style.display = 'none';
  chatSendText(text);
}
async function chatSendText(text){
  if(chatLoading) return;
  chatAddMsg('user', text);
  chatHistory.push({role:'user', content:text});
  chatLoading = true;
  document.getElementById('chatSendBtn').disabled = true;
  var typingId = 'typing_'+Date.now();
  chatAddMsg('bot', '__typing__', typingId);
  try {
    var res = await fetch('https://api.anthropic.com/v1/messages', {
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body: JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:1000,system:CHAT_SYSTEM,messages:chatHistory})
    });
    var data = await res.json();
    var reply = '';
    if(data.content && data.content.length){ data.content.forEach(function(b){ if(b.type==='text') reply+=b.text; }); }
    else { reply = "Sorry, I couldn't reach the support server. Please try again or email support@skibivote.ph."; }
    var typingEl = document.getElementById(typingId);
    if(typingEl) typingEl.remove();
    chatHistory.push({role:'assistant', content:reply});
    chatAddMsg('bot', reply);
  } catch(e){
    var typingEl = document.getElementById(typingId);
    if(typingEl) typingEl.remove();
    chatAddMsg('bot', "Connection error. Please check your network and try again.");
  }
  chatLoading = false;
  document.getElementById('chatSendBtn').disabled = false;
  chatScrollBottom();
}
function chatHandleKey(e){ if(e.key==='Enter' && !e.shiftKey){ e.preventDefault(); chatSend(); } }
function chatAutoResize(el){ el.style.height=''; el.style.height=Math.min(el.scrollHeight,70)+'px'; }

// ── TOAST ──
function toast(msg){
  var t = document.getElementById('toastEl');
  document.getElementById('toastMsg').textContent = msg;
  t.classList.add('show');
  clearTimeout(t._tid);
  t._tid = setTimeout(function(){ t.classList.remove('show'); }, 3000);
}
</script>
</body>
</html>
