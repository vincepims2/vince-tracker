[index-2.html](https://github.com/user-attachments/files/28430039/index-2.html)
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Vince Tracker">
<title>Vince Tracker</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent;}
body{font-family:'Poppins',sans-serif;background:#0d1117;min-height:100vh;color:#e2ddd4;padding-bottom:80px;}
body.session-active{padding-bottom:0;}
body.session-active .bottom-nav{display:none!important;}
.header{background:linear-gradient(160deg,#1a2035 0%,#0d1117 100%);border-bottom:1px solid #252d3d;padding:36px 16px 14px;}
.header-top{display:flex;justify-content:space-between;align-items:flex-start;}
.header-label{font-size:11px;letter-spacing:3px;color:#4a6a8a;text-transform:uppercase;margin-bottom:2px;}
.header-title{font-size:22px;font-weight:700;color:#e2ddd4;}
.summary-box{margin-top:12px;background:#141929;border-radius:14px;padding:14px 12px;border:1px solid #1e2535;}
.prog-row{display:flex;align-items:center;gap:4px;margin-bottom:5px;}
.prog-icon{font-size:13px;width:14px;text-align:center;}
.progress-bar{flex:1;height:7px;background:#1e2535;border-radius:4px;overflow:hidden;}
.progress-fill{height:100%;border-radius:4px;transition:width 0.5s;}
.prog-val{font-size:11px;font-weight:700;width:70px;text-align:right;white-space:nowrap;}
.meals-mini{display:flex;gap:5px;margin-top:10px;}
.meal-mini{flex:1;text-align:center;background:#0d1117;border-radius:8px;padding:6px 3px;border:1px solid #1e2535;}
.meal-mini-name{font-size:10px;color:#4a5a6a;margin-bottom:2px;font-weight:600;text-transform:uppercase;}
.meal-mini-p,.meal-mini-l,.meal-mini-g,.meal-mini-f{font-size:10px;font-weight:600;}
.date-row{display:flex;gap:8px;align-items:center;margin-top:10px;}
.date-btn{padding:5px 12px;background:#141929;color:#6a7a8a;border:1px solid #1e2535;border-radius:8px;font-size:13px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:500;}
.date-label{font-size:12px;color:#4a6a8a;flex:1;text-align:right;font-weight:500;}
.tabs{display:flex;border-bottom:1px solid #1e2535;background:#0d1117;position:sticky;top:0;z-index:10;}
.tab{flex:1;padding:11px 4px;font-size:11px;border:none;cursor:pointer;background:transparent;color:#4a5a6a;border-bottom:2px solid transparent;font-family:'Poppins',sans-serif;font-weight:600;letter-spacing:0.3px;text-transform:uppercase;}
.tab.active{background:#141929;color:#e2ddd4;border-bottom:2px solid #4a8abf;}
.bottom-nav{position:fixed;bottom:0;left:0;right:0;background:#0d1117;border-top:1px solid #1e2535;display:flex;z-index:20;padding-bottom:env(safe-area-inset-bottom);}
.nav-btn{flex:1;padding:10px 2px;border:none;background:transparent;color:#4a5a6a;cursor:pointer;font-family:'Poppins',sans-serif;font-size:8px;font-weight:600;letter-spacing:0.3px;text-transform:uppercase;display:flex;flex-direction:column;align-items:center;gap:3px;}
.nav-btn.active{color:#4a8abf;}
.nav-icon{font-size:16px;line-height:1;}
.content{padding:14px 16px;}
.meal-total{border-radius:12px;padding:12px 14px;margin-bottom:8px;border:1px solid #1e2535;}
.meal-total.ok{background:#141929;}.meal-total.warn{background:#1a1a0d;border-color:#4a4a1a;}.meal-total.alert{background:#1f1010;border-color:#5a2020;}
.meal-total-row{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:4px;}
.meal-total-name{font-size:13px;color:#6a7a8a;font-weight:600;}
.meal-total-nums{display:flex;gap:12px;}
.prot-val{font-size:14px;color:#4caf7d;font-weight:700;}
.lip-val{font-size:14px;font-weight:700;}
.gluc-val{font-size:14px;font-weight:700;color:#4a8abf;}
.lip-ok{color:#e07a7a;}.lip-warn{color:#e8c94a;}.lip-alert{color:#e85a4a;}
.alert-msg{margin-top:5px;font-size:11px;font-weight:500;}
.alert-msg.warn{color:#e8c94a;}.alert-msg.alert{color:#e85a4a;}
.save-btn{width:100%;padding:9px;background:#1a2a1a;color:#6ab06a;border:1px solid #2a4a2a;border-radius:9px;font-size:13px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;margin-bottom:8px;}
.food-item{display:flex;align-items:center;gap:8px;margin-bottom:6px;background:#141929;border-radius:10px;padding:9px 12px;border:1px solid #1e2535;}
.food-item-info{flex:1;}
.food-item-name{font-size:12px;color:#c8d0dc;font-weight:500;}
.food-item-macros{font-size:11px;color:#4a6a7a;margin-top:1px;font-weight:500;}
.food-item-actions{display:flex;gap:4px;}
.food-item-qty{background:#0d1117;border:1px solid #1e2535;border-radius:6px;padding:3px 7px;font-size:12px;color:#8a9ab0;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;}
.food-item-remove{background:none;border:none;color:#4a2a2a;cursor:pointer;font-size:18px;padding:0 2px;line-height:1;}
.undo-bar{background:#1a2535;border:1px solid #252d3d;border-radius:10px;padding:9px 14px;margin-bottom:8px;display:flex;justify-content:space-between;align-items:center;}
.undo-text{font-size:12px;color:#6a7a8a;font-weight:500;}
.undo-btn{background:#2a3f5a;color:#8ab0d0;border:none;border-radius:6px;padding:5px 12px;font-size:12px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;}
.section-title{font-size:11px;color:#4a5a6a;letter-spacing:2px;text-transform:uppercase;margin-bottom:8px;font-weight:600;}
.fav-panel{background:#141929;border-radius:12px;margin-bottom:8px;border:1px solid #1e2535;overflow:hidden;}
.fav-header{display:flex;justify-content:space-between;align-items:center;padding:11px 14px;cursor:pointer;}
.fav-header-label{font-size:12px;color:#6a7a8a;font-weight:600;}
.fav-header-arrow{font-size:13px;color:#4a5a6a;}
.fav-body{padding:0 14px 12px;}
.fav-grid{display:flex;flex-wrap:wrap;gap:7px;}
.fav-tag{background:#0d1117;border:1px solid #252d3d;border-radius:8px;padding:7px 10px;font-size:12px;color:#8a9ab0;cursor:pointer;display:inline-flex;align-items:center;gap:6px;font-weight:500;}
.fav-tag-del{color:#4a2a2a;font-size:15px;margin-left:2px;}
.fav-add-btn{background:#1a2535;border:1px dashed #252d3d;border-radius:8px;padding:7px 12px;font-size:12px;color:#4a6a8a;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:500;width:100%;margin-top:8px;text-align:center;}
.add-panel{background:#141929;border-radius:12px;padding:14px;border:1px solid #1e2535;}
.mode-toggle{display:flex;background:#0d1117;border-radius:10px;padding:3px;margin-bottom:12px;}
.mode-btn{flex:1;padding:7px 4px;font-size:11px;border:none;cursor:pointer;border-radius:8px;background:transparent;color:#4a5a6a;font-family:'Poppins',sans-serif;font-weight:600;}
.mode-btn.active{background:#1e2f4a;color:#e2ddd4;}
.food-search{width:100%;background:#0d1117;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:9px 12px;font-size:13px;margin-bottom:8px;font-family:'Poppins',sans-serif;}
.food-search::placeholder{color:#3a4a5a;}
.food-list{max-height:190px;overflow-y:auto;margin-bottom:8px;border-radius:9px;border:1px solid #1e2535;}
.food-list-item{display:flex;align-items:center;justify-content:space-between;padding:8px 12px;background:#0d1117;border-bottom:1px solid #141929;cursor:pointer;}
.food-list-item:last-child{border-bottom:none;}
.food-list-item.selected{background:#1a2535;}
.food-list-name{font-size:12px;color:#c8d0dc;font-weight:500;flex:1;}
.food-list-macros{font-size:11px;color:#4a6a7a;font-weight:500;margin-left:8px;white-space:nowrap;}
.food-list-del{background:none;border:none;color:#3a2a2a;cursor:pointer;font-size:15px;padding:0 4px;margin-left:4px;}
input[type=text],input[type=number]{background:#0d1117;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:9px 12px;font-size:13px;font-family:'Poppins',sans-serif;width:100%;}
textarea{width:100%;background:#0d1117;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:8px 12px;font-size:12px;font-family:'Poppins',sans-serif;resize:vertical;}
input::placeholder,textarea::placeholder{color:#3a4a5a;}
.custom-name{margin-bottom:8px;}
.custom-row{display:flex;gap:8px;margin-bottom:8px;}
.custom-row input{flex:1;}
.qty-row{display:flex;gap:8px;align-items:center;margin-top:10px;}
.qty-ctrl{display:flex;align-items:center;gap:4px;background:#0d1117;border-radius:9px;padding:5px 8px;border:1px solid #1e2535;}
.qty-btn{background:none;border:none;color:#6a7a8a;cursor:pointer;font-size:20px;line-height:1;padding:0 3px;}
.qty-input{font-size:14px;color:#e2ddd4;width:46px;text-align:center;background:transparent;border:none;font-family:'Poppins',sans-serif;font-weight:600;}
.qty-input:focus{outline:none;}
.add-btn{flex:1;padding:11px;background:linear-gradient(135deg,#2a4a7a,#1a3a5a);color:#e2ddd4;border:none;border-radius:9px;font-size:14px;cursor:pointer;font-weight:700;font-family:'Poppins',sans-serif;}
.custom-food-list{margin-top:10px;}
.custom-food-header{font-size:11px;color:#3a4a5a;letter-spacing:1px;text-transform:uppercase;margin-bottom:6px;font-weight:600;}
.custom-food-tag{display:inline-flex;align-items:center;gap:4px;background:#141929;border:1px solid #1e2f3e;border-radius:7px;padding:4px 8px;margin:3px;font-size:11px;color:#6a7a8a;cursor:pointer;font-weight:500;}
.custom-food-del{color:#3a2a2a;font-size:14px;margin-left:2px;}
.weight-panel{background:#141929;border-radius:14px;padding:14px;margin-top:8px;border:1px solid #1e2535;}
.weight-input-row{display:flex;gap:8px;align-items:center;margin-bottom:14px;}
.weight-input-row input{flex:1;}
.weight-save-btn{padding:10px 14px;background:linear-gradient(135deg,#2a4a7a,#1a3a5a);color:#e2ddd4;border:none;border-radius:9px;font-size:13px;cursor:pointer;font-weight:700;font-family:'Poppins',sans-serif;white-space:nowrap;}
.weight-chart{background:#0d1117;border-radius:10px;padding:12px;border:1px solid #1e2535;margin-bottom:12px;}
.weight-chart-title{font-size:11px;color:#4a5a6a;text-transform:uppercase;letter-spacing:1px;font-weight:600;margin-bottom:10px;}
.milestone{display:flex;justify-content:space-between;align-items:center;padding:8px 0;border-bottom:1px solid #1e2535;}
.milestone:last-child{border-bottom:none;}
.milestone-label{font-size:12px;color:#6a7a8a;font-weight:500;}
.milestone-value{font-size:12px;font-weight:700;}
.compact-cards{display:flex;gap:8px;margin-bottom:12px;}
.compact-card{flex:1;background:#141929;border:1px solid #1e2535;border-radius:12px;padding:10px 8px;text-align:center;}
.compact-card-label{font-size:9px;color:#4a5a6a;text-transform:uppercase;letter-spacing:1px;font-weight:600;margin-bottom:4px;}
.compact-card-val{font-size:15px;font-weight:700;}
.compact-card-sub{font-size:9px;color:#4a5a6a;margin-top:2px;font-weight:500;}
.stats-panel{background:#141929;border-radius:14px;padding:14px;border:1px solid #1e2535;margin-bottom:10px;}
.stats-grid{display:flex;gap:8px;}
.stat-box{flex:1;background:#0d1117;border-radius:10px;padding:10px 8px;text-align:center;border:1px solid #1e2535;}
.stat-label{font-size:10px;color:#4a5a6a;text-transform:uppercase;letter-spacing:1px;font-weight:600;margin-bottom:3px;}
.stat-value{font-size:16px;font-weight:700;}
.stat-sub{font-size:10px;color:#4a5a6a;margin-top:2px;font-weight:500;}
.backup-panel{background:#141929;border-radius:12px;padding:14px;margin-top:10px;border:1px solid #1e2535;}
.backup-btn{width:100%;padding:11px;border-radius:9px;font-size:13px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;margin-bottom:8px;border:1px solid #1e2535;}
.backup-export{background:#0d1f0d;color:#6ab06a;border-color:#1a3a1a;}
.backup-import{background:#0d1520;color:#6a8ab0;border-color:#1a2a3a;}
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,0.8);z-index:100;display:flex;align-items:flex-end;}
.modal{background:#141929;border-radius:18px 18px 0 0;padding:20px 16px 40px;width:100%;border-top:1px solid #1e2535;max-height:90vh;overflow-y:auto;}
.modal-title{font-size:15px;font-weight:700;color:#e2ddd4;margin-bottom:14px;text-align:center;}
.modal-btn{width:100%;padding:13px;border:none;border-radius:10px;font-size:14px;font-family:'Poppins',sans-serif;font-weight:600;cursor:pointer;margin-bottom:8px;}
.modal-confirm{background:#e85a4a;color:white;}
.modal-cancel{background:#1e2535;color:#8a9ab0;}
.modal-label{font-size:11px;color:#6a7a8a;font-weight:600;text-transform:uppercase;letter-spacing:1px;margin-bottom:6px;margin-top:12px;display:block;}
.toast{position:fixed;top:60px;left:50%;transform:translateX(-50%);background:#1a3a1a;color:#6ab06a;border:1px solid #2a4a2a;border-radius:10px;padding:10px 20px;font-size:13px;font-weight:600;font-family:'Poppins',sans-serif;z-index:200;opacity:0;transition:opacity 0.3s;pointer-events:none;}
.toast.show{opacity:1;}
/* MUSCU */
.gym-content{padding:14px 16px;}
.gym-top-row{display:flex;gap:8px;margin-bottom:10px;}
.gym-chip{background:#141929;border:1px solid #1e2535;border-radius:20px;padding:6px 8px;display:flex;align-items:center;gap:4px;flex:1;justify-content:center;}
.gym-chip-label{font-size:10px;color:#4a5a6a;font-weight:600;text-transform:uppercase;letter-spacing:1px;}
.gym-chip-val{font-size:14px;font-weight:700;color:#4a8abf;}
.gym-tractions-bar{background:#1a1a0d;border:1px solid #3a3a1a;border-radius:10px;padding:10px 14px;margin-bottom:10px;display:flex;align-items:center;justify-content:space-between;cursor:pointer;}
.gym-tractions-left{display:flex;align-items:center;gap:8px;}
.gym-tractions-icon{font-size:16px;}
.gym-tractions-info{display:flex;flex-direction:column;}
.gym-tractions-label{font-size:10px;color:#5a5a3a;font-weight:600;text-transform:uppercase;letter-spacing:1px;}
.gym-tractions-val{font-size:15px;font-weight:700;color:#e8c94a;}
.gym-tractions-edit{font-size:11px;color:#4a4a2a;font-weight:500;}
.gym-suggest{background:#1a2a1a;border:1px solid #2a4a2a;border-radius:10px;padding:10px 14px;margin-bottom:10px;display:flex;justify-content:space-between;align-items:center;cursor:pointer;}
.gym-suggest-tag{font-size:9px;color:#4a6a4a;font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:2px;}
.gym-suggest-name{font-size:13px;color:#6ab06a;font-weight:700;}
.gym-week-row{display:flex;gap:3px;margin-bottom:12px;}
.gym-week-day{flex:1;text-align:center;background:#141929;border-radius:8px;padding:6px 2px;border:1px solid #1e2535;}
.gym-week-day.today{border-color:#4a8abf;}
.gym-week-day-name{font-size:7px;color:#4a5a6a;font-weight:600;text-transform:uppercase;margin-bottom:3px;}
.gym-week-day-dot{width:8px;height:8px;border-radius:50%;margin:0 auto 2px;}
.gym-week-day-label{font-size:7px;font-weight:600;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}
.gym-card{background:#141929;border-radius:14px;padding:12px 14px;margin-bottom:8px;border:1px solid #1e2535;cursor:pointer;}
.gym-card-top{display:flex;justify-content:space-between;align-items:flex-start;}
.gym-card-name{font-size:13px;font-weight:700;color:#e2ddd4;}
.gym-card-right{display:flex;flex-direction:column;align-items:flex-end;gap:3px;}
.gym-rec-dot{width:11px;height:11px;border-radius:50%;flex-shrink:0;}
.gym-rec-green{background:#4caf7d;}.gym-rec-orange{background:#e8c94a;}.gym-rec-red{background:#e85a4a;}
.gym-rec-label{font-size:10px;font-weight:600;}
.gym-rec-label.green{color:#4caf7d;}.gym-rec-label.orange{color:#e8c94a;}.gym-rec-label.red{color:#e85a4a;}
.gym-card-bottom{display:flex;align-items:center;gap:8px;margin-top:6px;flex-wrap:wrap;}
.gym-days-ago{font-size:10px;color:#4a5a6a;font-weight:500;}
.gym-mood-badge{font-size:13px;}
.gym-upgrade-badge{background:#1a3a1a;color:#4caf7d;border-radius:5px;padding:1px 6px;font-size:9px;font-weight:700;}
.gym-back-btn{display:inline-flex;align-items:center;gap:6px;background:transparent;border:none;color:#6a7a8a;font-size:12px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;margin-bottom:12px;padding:4px 0;}
.gym-group-title{font-size:18px;font-weight:700;color:#e2ddd4;margin-bottom:10px;}
/* Bloc récup groupe — NEW */
.gym-rec-block{background:#0d1117;border-radius:10px;padding:11px 14px;margin-bottom:14px;border:1px solid #1e2535;display:flex;align-items:center;gap:10px;}
.gym-rec-block-dot{width:12px;height:12px;border-radius:50%;flex-shrink:0;}
.gym-rec-block-info{flex:1;}
.gym-rec-block-main{font-size:14px;font-weight:700;}
.gym-rec-block-sub{font-size:10px;color:#4a5a6a;margin-top:2px;}
.gym-rec-edit-btn{background:#141929;border:1px solid #1e2535;border-radius:7px;padding:4px 9px;font-size:10px;color:#6a7a8a;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;flex-shrink:0;}
.gym-section-label{font-size:10px;color:#4a5a6a;letter-spacing:2px;text-transform:uppercase;font-weight:700;margin:12px 0 6px;}
.gym-ex-card{background:#141929;border-radius:10px;padding:10px 12px;margin-bottom:5px;border:1px solid #1e2535;}
.gym-ex-warmup{background:#131320;border-color:#1e1e35;}
.gym-ex-row{display:flex;align-items:center;gap:6px;}
.gym-ex-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:500;line-height:1.3;}
.gym-ex-meta{display:flex;align-items:center;gap:3px;flex-shrink:0;}
.gym-ex-ctrl{display:flex;align-items:center;gap:2px;background:#0d1117;border:1px solid #1e2535;border-radius:7px;padding:2px 3px;}
.gym-ctrl-btn{background:none;border:none;color:#6a7a8a;font-size:15px;cursor:pointer;padding:0 3px;line-height:1;font-weight:700;}
.gym-ex-val{font-size:11px;color:#8ab0d0;font-weight:700;min-width:24px;text-align:center;}
.gym-icon-btn{background:none;border:none;color:#3a5a7a;font-size:15px;cursor:pointer;padding:0 3px;flex-shrink:0;}
.gym-icon-btn.edit{color:#5a7a3a;}
.gym-icon-btn.order{color:#4a5a6a;font-size:13px;}
.gym-start-btn{width:100%;padding:14px;background:linear-gradient(135deg,#1a3a1a,#0d2a0d);color:#4caf7d;border:1px solid #2a5a2a;border-radius:12px;font-size:15px;cursor:pointer;font-weight:700;font-family:'Poppins',sans-serif;margin-top:12px;}
.gym-add-ex-btn{width:100%;padding:10px;background:transparent;color:#4a8abf;border:1px dashed #2a4a6a;border-radius:9px;font-size:12px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;margin-top:6px;}
.gym-reset-btn{width:100%;padding:8px;background:transparent;color:#3a4a5a;border:1px dashed #252d3d;border-radius:9px;font-size:11px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:500;margin-top:6px;}
/* Session */
.session-wrap{min-height:100vh;padding:16px;background:#0d1117;}
.session-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:10px;padding-top:env(safe-area-inset-top,20px);}
.session-group-name{font-size:16px;font-weight:700;color:#e2ddd4;}
.session-exit{background:transparent;border:none;color:#4a5a6a;font-size:12px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;}
.session-progress-bar{background:#1e2535;border-radius:4px;height:5px;margin-bottom:14px;overflow:hidden;}
.session-progress-fill{height:100%;background:linear-gradient(90deg,#4caf7d,#2a8a5a);border-radius:4px;transition:width 0.4s;}
.session-progress-label{font-size:10px;color:#4a6a5a;font-weight:600;text-align:right;margin-bottom:4px;}
.session-ex-item{background:#141929;border-radius:10px;padding:11px 13px;margin-bottom:5px;border:1px solid #1e2535;transition:background 0.2s,opacity 0.2s;}
.session-ex-item.ex-done{background:#0d1a0d;border-color:#2a5a2a;opacity:0.65;}
.session-ex-warmup{background:#131320;border-color:#1e1e35;}
.session-ex-row{display:flex;align-items:center;gap:8px;}
.session-ex-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:600;line-height:1.3;}
.session-ex-ctrl{display:flex;align-items:center;gap:2px;background:#0d1117;border:1px solid #1e2535;border-radius:7px;padding:2px 4px;}
.session-ctrl-btn{background:none;border:none;color:#6a7a8a;font-size:14px;cursor:pointer;padding:0 3px;line-height:1;font-weight:700;}
.session-ctrl-val{font-size:11px;color:#8ab0d0;font-weight:700;min-width:24px;text-align:center;}
.session-check-btn{background:none;border:2px solid #2a4a3a;border-radius:50%;width:28px;height:28px;cursor:pointer;font-size:13px;display:flex;align-items:center;justify-content:center;flex-shrink:0;color:#3a5a4a;transition:all 0.15s;}
.session-check-btn.done{background:#1a4a1a;border-color:#4caf7d;color:#4caf7d;}
.session-end-btn{width:100%;padding:14px;background:linear-gradient(135deg,#3a1a1a,#2a0d0d);color:#e85a4a;border:1px solid #5a2a2a;border-radius:12px;font-size:15px;cursor:pointer;font-weight:700;font-family:'Poppins',sans-serif;margin-top:14px;}
/* Mood/stretch */
.mood-btn{width:100%;padding:14px;border-radius:12px;font-size:15px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:700;margin-bottom:10px;border:1px solid;}
.mood-bien{background:#1a3a1a;color:#4caf7d;border-color:#2a5a2a;}
.mood-moyen{background:#2a2a1a;color:#e8c94a;border-color:#3a3a1a;}
.mood-dur{background:#2a1a1a;color:#e85a4a;border-color:#3a1a1a;}
.stretch-item{background:#0d1117;border-radius:10px;padding:12px 14px;margin-bottom:8px;border:1px solid #1e2535;}
.stretch-name{font-size:13px;font-weight:700;color:#e2ddd4;margin-bottom:5px;}
.stretch-info{font-size:11px;color:#6a7a8a;line-height:1.6;}
/* Perso */
.perso-name-input{width:100%;background:#141929;color:#e2ddd4;border:1px solid #1e2535;border-radius:9px;padding:10px 14px;font-size:14px;font-family:'Poppins',sans-serif;font-weight:600;margin-bottom:12px;}
.perso-ex-item{background:#141929;border-radius:10px;padding:10px 12px;margin-bottom:5px;border:1px solid #1e2535;display:flex;align-items:center;gap:6px;}
.perso-ex-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:500;}
.perso-ex-info{font-size:10px;color:#4a5a6a;}
.perso-remove-btn{background:none;border:none;color:#4a2a2a;cursor:pointer;font-size:18px;padding:0 2px;line-height:1;}
.perso-saved-item{background:#141929;border-radius:10px;padding:10px 14px;margin-bottom:6px;border:1px solid #1e2535;display:flex;justify-content:space-between;align-items:center;cursor:pointer;}
.perso-saved-name{font-size:13px;color:#e2ddd4;font-weight:600;}
.perso-saved-count{font-size:11px;color:#4a5a6a;}
.perso-del-btn{background:none;border:none;color:#4a2a2a;cursor:pointer;font-size:16px;padding:0 4px;}
/* Library */
.lib-filter-row{display:flex;gap:6px;overflow-x:auto;padding-bottom:4px;margin-bottom:8px;-webkit-overflow-scrolling:touch;}
.lib-filter-row::-webkit-scrollbar{display:none;}
.lib-filter-btn{white-space:nowrap;padding:5px 10px;border-radius:20px;border:1px solid #1e2535;background:#141929;color:#6a7a8a;font-size:11px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;flex-shrink:0;}
.lib-filter-btn.active{background:#1e2f4a;color:#8ab0d0;border-color:#2a4a6a;}
.lib-search{width:100%;background:#0d1117;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:9px 12px;font-size:13px;margin-bottom:8px;font-family:'Poppins',sans-serif;}
.lib-list{max-height:240px;overflow-y:auto;border:1px solid #1e2535;border-radius:9px;}
.lib-item{display:flex;align-items:center;padding:9px 12px;border-bottom:1px solid #0d1117;background:#141929;}
.lib-item:last-child{border-bottom:none;}
.lib-item-tag{font-size:9px;color:#4a6a8a;font-weight:700;text-transform:uppercase;background:#0d1117;border-radius:4px;padding:1px 5px;margin-right:8px;white-space:nowrap;flex-shrink:0;}
.lib-item-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:500;}
.lib-item-eq{font-size:10px;color:#4a5a6a;margin-left:6px;flex-shrink:0;}
.lib-item-add{background:#1a3a1a;border:1px solid #2a5a2a;color:#4caf7d;border-radius:6px;padding:3px 8px;font-size:13px;font-weight:700;cursor:pointer;font-family:'Poppins',sans-serif;flex-shrink:0;}
/* Aléatoire */
.alea-type-row{display:flex;flex-direction:column;gap:8px;margin-bottom:14px;}
.alea-type-btn{padding:14px;border-radius:12px;border:1px solid #1e2535;background:#141929;color:#c8d0dc;text-align:left;cursor:pointer;font-family:'Poppins',sans-serif;}
.alea-type-btn.active{border-color:#4a8abf;background:#1a2535;}
.alea-type-title{font-size:13px;font-weight:700;margin-bottom:3px;}
.alea-type-sub{font-size:11px;color:#6a7a8a;}
.alea-result-ex{background:#141929;border-radius:10px;padding:9px 12px;margin-bottom:5px;border:1px solid #1e2535;}
.alea-result-name{font-size:12px;color:#c8d0dc;font-weight:600;}
.alea-result-meta{font-size:10px;color:#4a5a6a;margin-top:2px;}
.slider-wrap{margin:10px 0;}
.slider-label{font-size:12px;color:#8ab0d0;font-weight:700;margin-bottom:6px;text-align:center;}
input[type=range]{width:100%;accent-color:#4a8abf;cursor:pointer;}
.group-select{width:100%;background:#141929;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:10px 12px;font-size:13px;font-family:'Poppins',sans-serif;margin-bottom:10px;cursor:pointer;}
.weight-chip{display:inline-flex;align-items:center;gap:3px;background:#1a2535;border:1px solid #2a3a5a;border-radius:6px;padding:2px 6px;font-size:10px;color:#6a8ab0;font-weight:600;cursor:pointer;margin-left:4px;flex-shrink:0;}
.traction-history-row{display:flex;justify-content:space-between;align-items:center;padding:6px 0;border-bottom:1px solid #1e2535;font-size:12px;}
.traction-history-row:last-child{border-bottom:none;}
.traction-history-date{color:#4a5a6a;font-weight:500;}
.traction-history-val{color:#e8c94a;font-weight:700;}
.gym-linked-badge{font-size:9px;color:#5a6a7a;font-weight:500;font-style:italic;}
.gym-idle-badge{background:#2a1a1a;color:#e8943a;border-radius:5px;padding:1px 6px;font-size:9px;font-weight:700;}
.past-date-btn{flex:1;padding:8px 4px;border-radius:8px;border:1px solid #1e2535;background:#141929;color:#6a7a8a;font-size:11px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;}
.past-date-btn.active{background:#1e2f4a;color:#8ab0d0;border-color:#2a4a6a;}
.past-mood-btn{flex:1;padding:9px 4px;border-radius:8px;border:1px solid #1e2535;background:#141929;color:#6a7a8a;font-size:12px;cursor:pointer;font-family:'Poppins',sans-serif;font-weight:600;}
.past-mood-btn.active{background:#1a3a1a;color:#4caf7d;border-color:#2a5a2a;}
.gym-session-row{display:flex;align-items:center;gap:10px;padding:9px 0;border-bottom:1px solid #1e2535;}
.gym-session-row:last-child{border-bottom:none;}
.gym-session-date{font-size:10px;color:#4a5a6a;font-weight:500;min-width:55px;}
.gym-session-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:600;}
.gym-session-mood{font-size:14px;}
.gym-action-row{display:flex;gap:8px;margin-bottom:12px;}
.gym-action-btn{flex:1;padding:10px 6px;border-radius:10px;border:1px solid #1e2535;background:#141929;color:#c8d0dc;font-size:11px;font-family:'Poppins',sans-serif;font-weight:600;cursor:pointer;text-align:center;}
.gym-action-btn.perso{border-color:#2a4a6a;color:#4a8abf;background:#0d1520;}
.gym-action-btn.alea{border-color:#4a2a6a;color:#8a6abf;background:#150d20;}
/* ══ RECUP ══ */
.recup-activity{background:#141929;border-radius:12px;padding:13px 14px;margin-bottom:8px;border:1px solid #1e2535;}
.recup-activity-header{display:flex;align-items:center;justify-content:space-between;gap:8px;margin-bottom:5px;}
.recup-activity-name{font-size:13px;font-weight:700;color:#e2ddd4;flex:1;}
.recup-badge{font-size:9px;font-weight:700;border-radius:5px;padding:2px 8px;white-space:nowrap;}
.recup-benefit{font-size:11px;color:#6a7a8a;line-height:1.5;margin-bottom:8px;}
.recup-footer{display:flex;align-items:center;justify-content:space-between;}
.recup-duration{font-size:10px;color:#4a5a6a;font-weight:600;}
.recup-log-btn{padding:5px 14px;border-radius:7px;border:none;font-size:11px;font-family:'Poppins',sans-serif;font-weight:700;cursor:pointer;background:#1a3a1a;color:#4caf7d;border:1px solid #2a5a2a;}
.recup-log-row{display:flex;align-items:center;gap:10px;padding:9px 0;border-bottom:1px solid #1e2535;}
.recup-log-row:last-child{border-bottom:none;}
.recup-log-date{font-size:10px;color:#4a5a6a;font-weight:500;min-width:48px;}
.recup-log-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:600;}
.recup-log-del{background:none;border:none;color:#3a2a2a;cursor:pointer;font-size:16px;padding:0 4px;}
/* ══ RECUP V2 ══ */
.recup-nav-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:12px;}
.recup-nav-card{background:#141929;border-radius:12px;padding:12px 10px;border:1px solid #1e2535;cursor:pointer;text-align:center;transition:border-color 0.2s;}
.recup-nav-card:active{border-color:#4a8abf;}
.recup-nav-card-icon{font-size:22px;margin-bottom:4px;}
.recup-nav-card-label{font-size:12px;font-weight:700;color:#e2ddd4;}
.recup-nav-card-sub{font-size:10px;color:#4a5a6a;margin-top:2px;}
.recup-prog-card{background:#141929;border-radius:14px;padding:13px 14px;margin-bottom:8px;border:1px solid #1e2535;cursor:pointer;border-left:3px solid #2a4a6a;}
.recup-prog-header{display:flex;align-items:center;gap:10px;}
.recup-prog-icon{font-size:20px;flex-shrink:0;}
.recup-prog-info{flex:1;}
.recup-prog-name{font-size:14px;font-weight:700;color:#e2ddd4;}
.recup-prog-meta{font-size:10px;color:#4a5a6a;margin-top:2px;}
.recup-prog-desc{font-size:11px;color:#5a6a7a;margin-top:6px;line-height:1.4;}
.recup-suggest-box{background:#141929;border-radius:12px;padding:12px 14px;margin-bottom:12px;border-left:3px solid #4a8abf;border-top:1px solid #1e2535;border-right:1px solid #1e2535;border-bottom:1px solid #1e2535;}
.recup-suggest-title{font-size:10px;color:#4a8abf;font-weight:700;text-transform:uppercase;letter-spacing:1px;margin-bottom:8px;}
.recup-suggest-item{font-size:12px;color:#c8d0dc;padding:3px 0;font-weight:500;}
.recup-ex-card{background:#0d1117;border-radius:10px;padding:11px 12px;margin-bottom:6px;border:1px solid #1e2535;display:flex;align-items:center;gap:8px;}
.recup-ex-cat{font-size:9px;font-weight:700;text-transform:uppercase;letter-spacing:1px;border-radius:4px;padding:2px 6px;white-space:nowrap;flex-shrink:0;}
.recup-ex-info{flex:1;min-width:0;}
.recup-ex-name{font-size:12px;font-weight:600;color:#c8d0dc;}
.recup-ex-meta{font-size:10px;color:#4a5a6a;margin-top:2px;}
.recup-ex-badges{display:flex;gap:4px;margin-top:3px;flex-wrap:wrap;}
.recup-badge-level{font-size:9px;border-radius:4px;padding:1px 5px;font-weight:700;}
.recup-badge-bilat{font-size:9px;color:#8a6abf;background:#1a1535;border-radius:4px;padding:1px 5px;font-weight:700;}
.recup-badge-timer{font-size:9px;color:#4a8abf;background:#0d1520;border-radius:4px;padding:1px 5px;font-weight:700;}
.recup-fav-btn{background:none;border:none;cursor:pointer;font-size:15px;padding:0 1px;opacity:0.5;}
.recup-fav-btn.active{opacity:1;}
/* Session récup */
.recup-session-wrap{padding:14px 16px;min-height:100vh;}
.recup-session-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:10px;}
.recup-session-name{font-size:16px;font-weight:700;color:#e2ddd4;}
.recup-session-exit{background:transparent;border:1px solid #2a3a4a;border-radius:8px;color:#6a7a8a;font-size:12px;cursor:pointer;padding:6px 12px;font-family:Poppins,sans-serif;font-weight:600;}
.recup-session-progress-label{font-size:11px;color:#4a6a8a;font-weight:600;margin-bottom:4px;}
.recup-session-progress-bar{height:5px;background:#1e2535;border-radius:3px;overflow:hidden;margin-bottom:14px;}
.recup-session-progress-fill{height:100%;background:linear-gradient(90deg,#6ab06a,#4caf7d);border-radius:3px;transition:width 0.4s;}
.recup-session-item{background:#141929;border-radius:12px;padding:12px 14px;margin-bottom:8px;border:1px solid #1e2535;border-left:3px solid #1e2535;}
.recup-session-item.done{opacity:0.55;border-left-color:#2a5a2a;}
.recup-session-item-row{display:flex;align-items:center;gap:8px;}
.recup-check-btn{width:28px;height:28px;border-radius:50%;border:2px solid #2a4a3a;background:transparent;color:#4a6a5a;font-size:14px;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;font-family:Poppins,sans-serif;}
.recup-check-btn.done{background:#1a3a1a;border-color:#4caf7d;color:#4caf7d;}
.recup-session-end-btn{width:100%;padding:14px;background:linear-gradient(135deg,#1a4a1a,#0d2a0d);color:#4caf7d;border:1px solid #2a5a2a;border-radius:12px;font-size:15px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif;margin-top:10px;}
/* Timer */
.recup-timer-btn{background:#0d1520;border:1px solid #1e2f4a;border-radius:6px;padding:3px 8px;font-size:11px;color:#4a8abf;cursor:pointer;font-family:Poppins,sans-serif;font-weight:600;flex-shrink:0;}
.recup-timer-btn.running{background:#0d201a;border-color:#2a5a3a;color:#4caf7d;}
.recup-timer-display{font-size:13px;font-weight:700;color:#4caf7d;min-width:36px;text-align:center;}
/* Log row amélioré */
.recup-log-row{display:flex;align-items:center;gap:8px;padding:9px 0;border-bottom:1px solid #1e2535;}
.recup-log-row:last-child{border-bottom:none;}
.recup-log-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;}
.recup-log-date{font-size:10px;color:#4a5a6a;font-weight:500;min-width:40px;}
.recup-log-name{flex:1;font-size:12px;color:#c8d0dc;font-weight:600;}
.recup-log-dur{font-size:10px;color:#4a5a6a;white-space:nowrap;}
/* Activité dot systeme */
.recup-activity{background:#141929;border-radius:12px;padding:13px 14px;margin-bottom:8px;border:1px solid #1e2535;border-left:3px solid #1e2535;}
.recup-activity.green{border-left-color:#4caf7d;}
.recup-activity.orange{border-left-color:#e8c94a;}
.recup-activity.red{border-left-color:#e85a4a;opacity:0.75;}
.recup-activity-header{display:flex;align-items:center;gap:8px;margin-bottom:5px;}
.recup-activity-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0;}
.recup-activity-name{font-size:13px;font-weight:700;color:#e2ddd4;flex:1;}
.recup-benefit{font-size:11px;color:#6a7a8a;line-height:1.5;margin-bottom:8px;}
.recup-footer{display:flex;align-items:center;justify-content:space-between;}
.recup-duration{font-size:10px;color:#4a5a6a;font-weight:600;}
.recup-log-btn{padding:5px 14px;border-radius:7px;border:none;font-size:11px;font-family:'Poppins',sans-serif;font-weight:700;cursor:pointer;background:#1a3a1a;color:#4caf7d;border:1px solid #2a5a2a;}
.recup-legend{display:flex;gap:12px;margin-bottom:10px;font-size:10px;color:#4a5a6a;font-weight:600;}
.recup-legend-item{display:flex;align-items:center;gap:4px;}
</style>
</head>
<body>
<div class="header" id="main-header" style="display:none">
  <div class="header-top"><div><div class="header-label">Suivi nutritionnel</div><div class="header-title">Vince Tracker</div></div></div>
  <div class="summary-box"><div id="prog-bars"></div><div class="meals-mini" id="meals-mini"></div></div>
  <div class="date-row">
    <button class="date-btn" onclick="prevDay()">◀</button>
    <span class="date-label" id="date-label"></span>
    <button class="date-btn" onclick="nextDay()">▶</button>
  </div>
</div>
<div class="tabs" id="tabs" style="display:none"></div>
<div id="main-content"></div>
<div class="bottom-nav">
  <button class="nav-btn active" id="nav-repas" onclick="switchView('repas')"><span class="nav-icon">🍽️</span>Repas</button>
  <button class="nav-btn" id="nav-muscu" onclick="switchView('muscu')"><span class="nav-icon">🏋️</span>Muscu</button>
  <button class="nav-btn" id="nav-recup" onclick="switchView('recup')"><span class="nav-icon">🧘</span>Récup</button>
  <button class="nav-btn" id="nav-poids" onclick="switchView('poids')"><span class="nav-icon">⚖️</span>Poids</button>
  <button class="nav-btn" id="nav-data" onclick="switchView('data')"><span class="nav-icon">💾</span>Data</button>
</div>
<div class="toast" id="toast"></div>
<div class="modal-overlay" id="modal" style="display:none"><div class="modal">
  <div class="modal-title" id="modal-title">Confirmer</div>
  <button class="modal-btn modal-confirm" id="modal-confirm">Confirmer</button>
  <button class="modal-btn modal-cancel" onclick="closeModal()">Annuler</button>
</div></div>
<div class="modal-overlay" id="qty-modal" style="display:none"><div class="modal">
  <div class="modal-title">Modifier la quantité</div>
  <input type="number" id="qty-modal-input" step="0.1" min="0.1" style="text-align:center;font-size:18px;font-weight:700;margin-bottom:12px">
  <button class="modal-btn" style="background:#2a4a7a;color:#e2ddd4" onclick="confirmQtyEdit()">✓ Valider</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('qty-modal').style.display='none'">Annuler</button>
</div></div>
<div class="modal-overlay" id="fav-modal" style="display:none"><div class="modal">
  <div class="modal-title">Nommer ce repas favori</div>
  <input type="text" id="fav-modal-name" placeholder="Ex: Petit-déj standard" style="margin-bottom:12px">
  <button class="modal-btn" style="background:#2a4a7a;color:#e2ddd4" onclick="confirmSaveFav()">💾 Sauvegarder</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('fav-modal').style.display='none'">Annuler</button>
</div></div>
<div class="modal-overlay" id="tractions-modal" style="display:none"><div class="modal">
  <div class="modal-title">🏆 Record tractions</div>
  <div style="font-size:12px;color:#6a7a8a;margin-bottom:12px;text-align:center">Reps max en une série (sans élastique)</div>
  <div style="display:flex;gap:10px;margin-bottom:12px">
    <div style="flex:1;text-align:center"><div style="font-size:10px;color:#4a5a6a;font-weight:600;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px">Reps max</div><input type="number" id="tractions-input" placeholder="Ex: 5" min="1" max="50" step="1" style="text-align:center;font-size:22px;font-weight:700;width:100%"></div>
    <div style="flex:1;text-align:center"><div style="font-size:10px;color:#4a5a6a;font-weight:600;text-transform:uppercase;letter-spacing:1px;margin-bottom:4px">Séries</div><input type="number" id="tractions-series-input" placeholder="Ex: 3" min="1" max="20" step="1" style="text-align:center;font-size:22px;font-weight:700;width:100%"></div>
  </div>
  <button class="modal-btn" style="background:#2a4a1a;color:#6ab06a" onclick="saveTractions()">✓ Enregistrer</button>
  <div id="tractions-history" style="margin-top:12px"></div>
  <button class="modal-btn modal-cancel" style="margin-top:8px" onclick="document.getElementById('tractions-modal').style.display='none'">Fermer</button>
</div></div>
<div class="modal-overlay" id="weight-kb-modal" style="display:none"><div class="modal">
  <div class="modal-title" id="weight-kb-title">Poids utilisé</div>
  <div style="font-size:12px;color:#6a7a8a;margin-bottom:10px;text-align:center">Kettlebell ou charge (kg)</div>
  <input type="number" id="weight-kb-input" placeholder="Ex: 12" min="0" max="100" step="0.5" style="text-align:center;font-size:22px;font-weight:700;margin-bottom:6px">
  <div style="font-size:11px;color:#4a5a6a;text-align:center;margin-bottom:12px">kg — laisser vide si poids du corps</div>
  <button class="modal-btn" style="background:#2a4a7a;color:#e2ddd4" onclick="saveExWeight()">✓ Enregistrer</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('weight-kb-modal').style.display='none'">Annuler</button>
</div></div>
<div class="modal-overlay" id="mood-modal" style="display:none"><div class="modal">
  <div class="modal-title">Comment s'est passée la séance ?</div>
  <button class="mood-btn mood-bien" onclick="selectMood('💪')">💪 Bien — en forme</button>
  <button class="mood-btn mood-moyen" onclick="selectMood('😐')">😐 Moyen — un peu fatigué</button>
  <button class="mood-btn mood-dur" onclick="selectMood('😓')">😓 Difficile — épuisé</button>
  <div style="margin-top:12px">
    <div style="font-size:10px;color:#4a5a6a;font-weight:600;text-transform:uppercase;letter-spacing:1px;margin-bottom:6px">Note rapide (optionnel)</div>
    <textarea id="session-note" rows="2" placeholder="Ex: dos tendu, montée en charge sur curl..." style="height:56px;resize:none"></textarea>
  </div>
</div></div>
<div class="modal-overlay" id="stretch-modal" style="display:none"><div class="modal">
  <div class="modal-title">🧘 Étirements post-séance</div>
  <div id="stretch-content"></div>
  <button class="modal-btn" style="background:#2a4a1a;color:#6ab06a;margin-top:8px" onclick="finishSession()">✓ Terminer la séance</button>
</div></div>
<div class="modal-overlay" id="info-modal" style="display:none"><div class="modal">
  <div class="modal-title" id="info-modal-title"></div>
  <div style="font-size:12px;color:#8a9ab0;line-height:1.7;margin-bottom:14px" id="info-modal-body"></div>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('info-modal').style.display='none'">OK</button>
</div></div>
<div class="modal-overlay" id="rec-modal" style="display:none"><div class="modal">
  <div class="modal-title">⏱ Temps de récupération</div>
  <div style="font-size:12px;color:#6a7a8a;margin-bottom:12px;text-align:center">Heures entre deux séances de ce groupe</div>
  <input type="number" id="rec-input" min="24" max="168" step="12" style="text-align:center;font-size:20px;font-weight:700;margin-bottom:6px">
  <div style="font-size:11px;color:#4a5a6a;text-align:center;margin-bottom:12px">heures</div>
  <button class="modal-btn" style="background:#2a4a7a;color:#e2ddd4" onclick="saveRecovery()">✓ Enregistrer</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('rec-modal').style.display='none'">Annuler</button>
</div></div>
<div class="modal-overlay" id="ex-modal" style="display:none"><div class="modal">
  <div class="modal-title" id="ex-modal-title">Exercice</div>
  <label class="modal-label">Nom</label>
  <input type="text" id="ex-name" placeholder="Nom" style="margin-bottom:4px">
  <label class="modal-label">Groupe musculaire ciblé</label>
  <input type="text" id="ex-group-target" placeholder="Ex: Dos, Biceps, Core..." style="margin-bottom:4px">
  <label class="modal-label">Équipement</label>
  <input type="text" id="ex-equipment" placeholder="Ex: Kettlebell, Élastique..." style="margin-bottom:4px">
  <div class="custom-row" style="margin-top:4px">
    <div style="flex:1"><label class="modal-label" style="margin-top:0">Séries</label><input type="number" id="ex-sets" min="1" max="10" style="text-align:center"></div>
    <div style="flex:1"><label class="modal-label" style="margin-top:0">Reps/sec</label><input type="number" id="ex-reps" min="1" max="120" style="text-align:center"></div>
    <div style="flex:1"><label class="modal-label" style="margin-top:0">Unité</label>
      <select id="ex-unit" style="width:100%;background:#0d1117;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:9px 8px;font-size:13px;font-family:Poppins,sans-serif">
        <option value="reps">reps</option><option value="sec">sec</option>
      </select>
    </div>
  </div>
  <label class="modal-label">Poids KB (kg) — optionnel</label>
  <input type="number" id="ex-weight" placeholder="Ex: 12" min="0" max="100" step="0.5" style="margin-bottom:4px">
  <label class="modal-label">Description</label>
  <textarea id="ex-info" rows="3" placeholder="Comment faire cet exercice..." style="margin-bottom:12px"></textarea>
  <button class="modal-btn" style="background:#2a5a2a;color:#6ab06a" onclick="saveExModal()">✓ Enregistrer</button>
  <button class="modal-btn" id="ex-delete-btn" style="background:#2a1a1a;color:#e85a4a" onclick="deleteExModal()">🗑 Supprimer</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('ex-modal').style.display='none'">Annuler</button>
</div></div>
<div class="modal-overlay" id="lib-modal" style="display:none"><div class="modal">
  <div class="modal-title">Ajouter un exercice</div>
  <div class="mode-toggle" style="margin-bottom:12px">
    <button class="mode-btn active" id="lib-tab-lib" onclick="switchLibTab('lib')">Bibliothèque</button>
    <button class="mode-btn" id="lib-tab-custom" onclick="switchLibTab('custom')">Créer</button>
  </div>
  <div id="lib-tab-content"></div>
  <button class="modal-btn modal-cancel" style="margin-top:6px" onclick="closeLibModal()">Fermer</button>
</div></div>
<div class="modal-overlay" id="perso-save-modal" style="display:none"><div class="modal">
  <div class="modal-title">Sauvegarder la séance</div>
  <input type="text" id="perso-save-name" placeholder="Nom de la séance..." style="margin-bottom:12px">
  <button class="modal-btn" style="background:#2a4a7a;color:#e2ddd4" onclick="confirmSavePerso()">💾 Sauvegarder</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('perso-save-modal').style.display='none'">Annuler</button>
</div></div>
<div class="modal-overlay" id="past-session-modal" style="display:none"><div class="modal">
  <div class="modal-title">➕ Ajouter une séance passée</div>
  <label class="modal-label">Groupe musculaire</label>
  <select id="past-gid" style="width:100%;background:#0d1117;color:#c8d0dc;border:1px solid #1e2535;border-radius:9px;padding:10px 12px;font-size:13px;font-family:Poppins,sans-serif;margin-bottom:4px">
    <option value="dos">🔙 Dos</option><option value="dos_epaules">🏋️ Dos + Épaules</option>
    <option value="pecs_triceps">🤜 Pectoraux + Triceps</option>
    <option value="jambes_fessiers">🦵 Jambes + Fessiers</option><option value="biceps_isole">🎯 Biceps isolé</option>
    <option value="_perso">🎯 Séance perso</option><option value="_alea">🎲 Séance aléatoire</option>
  </select>
  <label class="modal-label">Date</label>
  <div style="display:flex;gap:6px;margin-bottom:8px">
    <button class="past-date-btn active" id="past-date-auj" onclick="setPastDate(0)">Aujourd'hui</button>
    <button class="past-date-btn" id="past-date-hier" onclick="setPastDate(1)">Hier</button>
    <button class="past-date-btn" id="past-date-avh" onclick="setPastDate(2)">Avant-hier</button>
  </div>
  <input type="date" id="past-date-input" style="margin-bottom:4px;text-align:center" onchange="setPastDateCustom(this.value)">
  <label class="modal-label">Ressenti</label>
  <div style="display:flex;gap:8px;margin-bottom:14px">
    <button class="past-mood-btn active" id="past-mood-bien" onclick="setPastMood('💪')">💪 Bien</button>
    <button class="past-mood-btn" id="past-mood-moyen" onclick="setPastMood('😐')">😐 Moyen</button>
    <button class="past-mood-btn" id="past-mood-dur" onclick="setPastMood('😓')">😓 Difficile</button>
  </div>
  <button class="modal-btn" style="background:#2a5a2a;color:#6ab06a" onclick="savePastSession()">✓ Enregistrer</button>
  <button class="modal-btn modal-cancel" onclick="document.getElementById('past-session-modal').style.display='none'">Annuler</button>
</div></div>
<script>
// ══ EXERCISE LIBRARY ══
const EXERCISE_LIBRARY=[
  {id:'l_dead_hang',group:'dos',name:'Dead hang actif',equipment:'Chaise romaine',defaultSets:3,defaultReps:20,unit:'sec',info:'Suspendu à la barre, pousse les omoplates vers le bas sans plier les coudes. Actif, pas passif.'},
  {id:'l_dead_hang_p',group:'dos',name:'Dead hang passif',equipment:'Chaise romaine',defaultSets:3,defaultReps:30,unit:'sec',info:'Suspension complète sans engagement musculaire. Étirement passif de la colonne.'},
  {id:'l_traction_serree',group:'dos',name:'Tractions prise serrée',equipment:'Chaise romaine + Élastique',defaultSets:3,defaultReps:5,unit:'reps',info:'Mains proches. Tire les coudes vers les hanches. Grand dorsal ciblé.'},
  {id:'l_traction_large',group:'dos',name:'Tractions prise large',equipment:'Chaise romaine + Élastique',defaultSets:3,defaultReps:5,unit:'reps',info:'Mains à largeur épaules +20cm. Tire les coudes vers le bas et l\'extérieur.'},
  {id:'l_traction_neg',group:'dos',name:'Tractions négatives',equipment:'Chaise romaine',defaultSets:3,defaultReps:5,unit:'reps',info:'Monte avec un saut, descends LENTEMENT en 5 secondes.'},
  {id:'l_traction_iso',group:'dos',name:'Tractions isométriques',equipment:'Chaise romaine',defaultSets:3,defaultReps:20,unit:'sec',info:'Tiens en position haute. Contraction maximale isométrique.'},
  {id:'l_towel_hang',group:'dos',name:'Towel hang — grip',equipment:'Chaise romaine',defaultSets:3,defaultReps:20,unit:'sec',info:'Serviette sur la barre. Force la prise des doigts et avant-bras.'},
  {id:'l_rowing_e',group:'dos',name:'Rowing élastique buste penché',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Buste à 45°. Tire les coudes vers les hanches en gardant le dos droit.'},
  {id:'l_rowing_assis',group:'dos',name:'Rowing élastique assis',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Assis au sol, jambes tendues, élastique sous les pieds.'},
  {id:'l_rowing_kb',group:'dos',name:'Rowing kettlebell unilatéral',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Genou et main opposée appuyés sur une surface stable. Grand dorsal et rhomboïdes.'},
  {id:'l_superman',group:'dos',name:'Superman au sol',equipment:'',defaultSets:3,defaultReps:12,unit:'reps',info:'Allongé ventre au sol, lève simultanément bras et jambes. Maintiens 2 sec.'},
  {id:'l_ext_dorsale',group:'dos',name:'Extensions dorsales',equipment:'Chaise romaine',defaultSets:3,defaultReps:12,unit:'reps',info:'Chaise romaine. Érecteurs du rachis.'},
  {id:'l_hyperext',group:'dos',name:'Hyperextensions',equipment:'Chaise romaine',defaultSets:3,defaultReps:12,unit:'reps',info:'Descends le buste, remonte jusqu\'à l\'horizontale. Bas du dos et fessiers.'},
  {id:'l_rot_ext',group:'epaules',name:'Rotation externe élastique',equipment:'Élastique',defaultSets:3,defaultReps:15,unit:'reps',info:'Bras collé au corps, coude à 90°. Tire vers l\'extérieur lentement. Essentiel pour la santé des épaules.'},
  {id:'l_face_pull',group:'epaules',name:'Face pull élastique',equipment:'Élastique',defaultSets:3,defaultReps:15,unit:'reps',info:'Élastique à hauteur du visage. Tire vers le front en ouvrant les coudes. Anti-voutement.'},
  {id:'l_ytw',group:'epaules',name:'Y-T-W au sol (maintien 2s)',equipment:'',defaultSets:3,defaultReps:10,unit:'reps',info:'Allongé ventre au sol. Y=bras en V, T=bras perpendiculaires, W=coudes à 90°. MAINTIENS 2 sec.'},
  {id:'l_oiseau',group:'epaules',name:'Oiseau élastique',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Buste légèrement penché. Ouvre les bras en arc de cercle. Deltoïdes postérieurs.'},
  {id:'l_elev_lat',group:'epaules',name:'Élévation latérale élastique',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Debout sur l\'élastique. Monte les bras sur les côtés. Deltoïdes latéraux.'},
  {id:'l_elev_front',group:'epaules',name:'Élévation frontale élastique',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Monte les bras devant jusqu\'à l\'horizontale. Deltoïdes antérieurs.'},
  {id:'l_shrug',group:'epaules',name:'Shrug kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:12,unit:'reps',info:'Kettlebell à deux mains. Hausse les épaules vers les oreilles, maintiens 1 sec.'},
  {id:'l_press_kb_d',group:'epaules',name:'Press épaules kettlebell debout',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Kettlebell au niveau de l\'épaule. Pousse verticalement au-dessus de la tête.'},
  {id:'l_curl_kb',group:'biceps',name:'Curl biceps kettlebell',equipment:'Kettlebell',defaultSets:4,defaultReps:10,unit:'reps',info:'Paume vers le HAUT. Coude fixe. Montée explosive, descente en 3 secondes.'},
  {id:'l_curl_marteau',group:'biceps',name:'Curl marteau kettlebell',equipment:'Kettlebell',defaultSets:4,defaultReps:10,unit:'reps',info:'Prise NEUTRE (pouce vers le haut). Cible le brachial et l\'avant-bras.'},
  {id:'l_curl_conc',group:'biceps',name:'Curl concentré kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Assis, coude contre le genou. Mouvement pur du biceps.'},
  {id:'l_curl_incl',group:'biceps',name:'Curl incliné élastique',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Élastique fixé bas, angle vers l\'arrière. Meilleure amplitude.'},
  {id:'l_curl_iso',group:'biceps',name:'Curl isométrique kettlebell',equipment:'Kettlebell',defaultSets:2,defaultReps:30,unit:'sec',info:'Coude à 90°. Tiens SANS BOUGER. Contraction isométrique maximale.'},
  {id:'l_curl_21',group:'biceps',name:'Curl 21s kettlebell',equipment:'Kettlebell',defaultSets:2,defaultReps:21,unit:'reps',info:'7 reps demi-bas + 7 demi-haut + 7 amplitude complète.'},
  {id:'l_dips',group:'triceps',name:'Dips',equipment:'Chaise romaine',defaultSets:3,defaultReps:8,unit:'reps',info:'Coudes serrés. Descente jusqu\'à 90°. Triceps ciblé.'},
  {id:'l_ext_triceps',group:'triceps',name:'Extensions triceps kettlebell (nuque)',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Kettlebell à deux mains derrière la nuque, coudes près des oreilles.'},
  {id:'l_kickback',group:'triceps',name:'Kickback triceps élastique',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Buste à 45°. Coude fixe. Étends le bras vers l\'arrière. Contracte 1 sec.'},
  {id:'l_pompes_diam',group:'triceps',name:'Pompes diamant',equipment:'',defaultSets:3,defaultReps:8,unit:'reps',info:'Mains formant un losange. Coudes serrés. Triceps et pectoraux internes.'},
  {id:'l_skull_crusher',group:'triceps',name:'Skull crusher kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Allongé au sol. Kettlebell au-dessus, coudes fléchis vers le sol.'},
  {id:'l_pompes',group:'pecs',name:'Pompes classiques',equipment:'',defaultSets:3,defaultReps:10,unit:'reps',info:'Mains à largeur épaules +10cm. Descente lente 4 sec, pause 1 sec, remontée explosive.'},
  {id:'l_pompes_incl',group:'pecs',name:'Pompes inclinées',equipment:'Chaise romaine',defaultSets:3,defaultReps:10,unit:'reps',info:'Mains sur la chaise romaine. Pectoraux supérieurs.'},
  {id:'l_pompes_surelev',group:'pecs',name:'Pompes pieds surélevés',equipment:'Chaise romaine',defaultSets:3,defaultReps:8,unit:'reps',info:'Pieds sur la chaise (max 70cm). Pectoraux supérieurs.'},
  {id:'l_pompes_larges',group:'pecs',name:'Pompes larges',equipment:'',defaultSets:3,defaultReps:10,unit:'reps',info:'Mains beaucoup plus larges. Pectoraux externes.'},
  {id:'l_pompes_tempo',group:'pecs',name:'Pompes tempo (4-1-2)',equipment:'',defaultSets:3,defaultReps:8,unit:'reps',info:'4 sec descente, 1 sec pause en bas, 2 sec remontée. Temps sous tension.'},
  {id:'l_fly_e',group:'pecs',name:'Fly élastique debout',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Bras légèrement fléchis, ferme les bras devant toi. Pectoraux.'},
  {id:'l_floor_press',group:'pecs',name:'Press kettlebell sol',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Allongé au sol, kettlebell à deux mains. Sans banc — sécurisé.'},
  {id:'l_dead_bug',group:'core',name:'Dead bug (maintien 2s)',equipment:'',defaultSets:3,defaultReps:8,unit:'reps',info:'Sur le dos, bras au plafond, genoux à 90°. Descends bras + jambe opposés. Dos plaqué. MAINTIENS 2 sec.'},
  {id:'l_bird_dog',group:'core',name:'Bird dog (maintien 3s)',equipment:'',defaultSets:3,defaultReps:10,unit:'reps',info:'À 4 pattes. Étends bras droit + jambe gauche. Dos PLAT. MAINTIENS 3 sec.'},
  {id:'l_gainage',group:'core',name:'Gainage frontal',equipment:'',defaultSets:3,defaultReps:30,unit:'sec',info:'Avant-bras et orteils. Corps en ligne droite.'},
  {id:'l_gainage_lat',group:'core',name:'Gainage latéral',equipment:'',defaultSets:3,defaultReps:30,unit:'sec',info:'Avant-bras et côté du pied. Corps en ligne droite. 30 sec de chaque côté.'},
  {id:'l_crunch_inv',group:'core',name:'Crunch inversé',equipment:'',defaultSets:3,defaultReps:15,unit:'reps',info:'Allongé, jambes à 90°. Soulève les hanches en contractant les abdominaux bas.'},
  {id:'l_mountain_climber',group:'core',name:'Mountain climbers',equipment:'',defaultSets:3,defaultReps:20,unit:'reps',info:'Position de pompe. Ramène les genoux vers la poitrine en alternant. Cardio + core.'},
  {id:'l_rot_russe',group:'core',name:'Rotation russe kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:20,unit:'reps',info:'Assis en V, jambes légèrement relevées. Passe la KB d\'un côté à l\'autre. Obliques.'},
  {id:'l_goblet',group:'jambes',name:'Goblet squat kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'KB contre la poitrine. Descends LENTEMENT (3 sec), pause 2 sec en bas. Quadriceps et fessiers.'},
  {id:'l_squat_bulgare',group:'jambes',name:'Squat bulgare chaise romaine',equipment:'Chaise romaine',defaultSets:3,defaultReps:8,unit:'reps',info:'Pied arrière sur la chaise. Genou avant à 90°. 8 de chaque jambe.'},
  {id:'l_fentes_march',group:'jambes',name:'Fentes marchées',equipment:'',defaultSets:3,defaultReps:12,unit:'reps',info:'En marchant, alterne les fentes. Genou avant à 90°.'},
  {id:'l_fentes_lat',group:'jambes',name:'Fentes latérales',equipment:'',defaultSets:3,defaultReps:10,unit:'reps',info:'Grand pas sur le côté. Genou fléchi à 90°, autre jambe tendue. Adducteurs.'},
  {id:'l_step_up',group:'jambes',name:'Step up chaise romaine',equipment:'Chaise romaine',defaultSets:3,defaultReps:10,unit:'reps',info:'Pose le pied sur la chaise. Monte en poussant sur le TALON.'},
  {id:'l_squat_sumo',group:'jambes',name:'Squat sumo kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:12,unit:'reps',info:'Pieds très écartés, orteils vers l\'extérieur. KB entre les jambes. Adducteurs.'},
  {id:'l_wall_sit',group:'jambes',name:'Wall sit',equipment:'',defaultSets:3,defaultReps:45,unit:'sec',info:'Dos contre le mur, cuisses horizontales. Quadriceps en isométrie.'},
  {id:'l_leg_curl',group:'jambes',name:'Leg curl unilatéral élastique',equipment:'Élastique',defaultSets:3,defaultReps:12,unit:'reps',info:'Élastique autour de la cheville. Allongé ventre au sol. Ischio-jambiers.'},
  {id:'l_mollets',group:'jambes',name:'Élévation mollets debout',equipment:'',defaultSets:3,defaultReps:20,unit:'reps',info:'Debout, monte sur la pointe des pieds. Descends lentement.'},
  {id:'l_hip_thrust',group:'fessiers',name:'Hip thrust kettlebell',equipment:'Kettlebell',defaultSets:4,defaultReps:12,unit:'reps',info:'Dos sur surface stable, KB sur le bassin. Pousse les hanches vers le haut. CONTRACTE 2 sec en haut.'},
  {id:'l_hip_thrust_uni',group:'fessiers',name:'Hip thrust unilatéral',equipment:'Kettlebell',defaultSets:3,defaultReps:12,unit:'reps',info:'Même mouvement mais une jambe à la fois.'},
  {id:'l_pont',group:'fessiers',name:'Pont fessier bilatéral',equipment:'',defaultSets:3,defaultReps:15,unit:'reps',info:'Sur le dos. Soulève les hanches. Maintiens 2 sec en haut.'},
  {id:'l_pont_uni',group:'fessiers',name:'Pont fessier unilatéral',equipment:'',defaultSets:3,defaultReps:12,unit:'reps',info:'Une jambe tendue, pousse avec l\'autre. 12 de chaque jambe.'},
  {id:'l_donkey_kicks',group:'fessiers',name:'Donkey kicks',equipment:'',defaultSets:3,defaultReps:15,unit:'reps',info:'À 4 pattes, pousse la jambe vers le haut. Maintiens 1 sec. 15 de chaque jambe.'},
  {id:'l_clamshells',group:'fessiers',name:'Clamshells',equipment:'',defaultSets:3,defaultReps:15,unit:'reps',info:'Sur le côté, genoux pliés. Ouvre le genou supérieur vers le plafond. Fessier moyen.'},
  {id:'l_clamshells_e',group:'fessiers',name:'Clamshells élastique',equipment:'Élastique',defaultSets:3,defaultReps:15,unit:'reps',info:'Élastique autour des genoux. Même mouvement avec résistance.'},
  {id:'l_rdl',group:'fessiers',name:'Romanian deadlift kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:10,unit:'reps',info:'Jambes presque tendues, penche le buste en avant. Ischio-jambiers et fessiers.'},
  {id:'l_swing',group:'fessiers',name:'Swing kettlebell',equipment:'Kettlebell',defaultSets:3,defaultReps:20,unit:'reps',info:'Propulse avec les hanches (pas les bras). Fessiers et ischio-jambiers. Bras passifs.'},
  {id:'l_rot_bassin',group:'mobilite',name:'Rotation de bassin',equipment:'',defaultSets:2,defaultReps:10,unit:'reps',info:'Mains sur les hanches. Grands cercles. 10 dans chaque sens.'},
  {id:'l_cat_cow',group:'mobilite',name:'Cat-cow mobilité lombaire',equipment:'',defaultSets:2,defaultReps:12,unit:'reps',info:'À 4 pattes. Inspiration = dos en creux, expiration = dos en rond.'},
  {id:'l_thread_needle',group:'mobilite',name:'Thread the needle',equipment:'',defaultSets:2,defaultReps:8,unit:'reps',info:'À 4 pattes. Passe un bras sous le corps. Rotation thoracique. 8 de chaque côté.'},
  {id:'l_deep_squat',group:'mobilite',name:'Deep squat hold',equipment:'',defaultSets:3,defaultReps:30,unit:'sec',info:'Squat profond tenu. Talons au sol, dos droit. Mobilité hanche, cheville, dos.'},
  {id:'l_hip_flexor',group:'mobilite',name:'Fente basse hip flexor',equipment:'',defaultSets:2,defaultReps:30,unit:'sec',info:'Fente basse, genou arrière au sol. Pousse les hanches en avant. ESSENTIEL conducteurs.'},
  {id:'l_pigeon',group:'mobilite',name:'Étirement fessiers pigeon',equipment:'',defaultSets:2,defaultReps:45,unit:'sec',info:'Position du pigeon au sol. Fessiers profonds. 45 sec de chaque côté.'},
  {id:'l_mollets_debout',group:'mollets',name:'Élévation mollets debout',equipment:'',defaultSets:4,defaultReps:20,unit:'reps',info:'Debout, monte sur la pointe des pieds. Maintiens 1 sec. Descends LENTEMENT.'},
  {id:'l_seated_calf',group:'mollets',name:'Seated calf raise (KB sur genoux)',equipment:'Kettlebell',defaultSets:3,defaultReps:20,unit:'reps',info:'Assis, KB sur les genoux. Monte sur la pointe des pieds. Cible le soléaire.'},
  {id:'l_mollets_marche',group:'mollets',name:'Mollets sur marche',equipment:'Chaise romaine',defaultSets:3,defaultReps:15,unit:'reps',info:'Pointe des pieds sur le rebord. Descends le talon en dessous, puis monte.'},
  // ── HALTÈRES ─────────────────────────────────────────────────────────────
  // Biceps haltères
  {id:'l_curl_halt_alt',group:'biceps',name:'Curl haltères alterné debout',equipment:'Haltères',defaultSets:4,defaultReps:10,unit:'reps',info:'Debout, haltères en supination. Alterne bras gauche et droit. Coude fixe contre le corps. Montée explosive, descente 3 sec.'},
  {id:'l_curl_halt_sim',group:'biceps',name:'Curl haltères simultané debout',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Debout, les deux haltères en même temps. Supination complète au sommet. Descente lente et contrôlée en 3 sec.'},
  {id:'l_curl_halt_incl',group:'biceps',name:'Curl haltères incliné',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Assis sur un plan incliné à 60°. Bras pendants derrière le corps. Étirement maximal du biceps long. Amplitude complète.'},
  {id:'l_curl_pupitre_halt',group:'biceps',name:'Curl pupitre haltère unilatéral',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Coude posé sur l\'intérieur de la cuisse. Mouvement pur du biceps sans compensation. 10 reps de chaque bras.'},
  {id:'l_curl_halt_marteau_alt',group:'biceps',name:'Curl haltères marteau alterné',equipment:'Haltères',defaultSets:4,defaultReps:10,unit:'reps',info:'Prise neutre (pouce vers le haut). Alterne bras gauche et droit. Cible le brachial et le long supinateur.'},
  // Épaules haltères
  {id:'l_elev_lat_halt',group:'epaules',name:'Élévation latérale haltères',equipment:'Haltères',defaultSets:3,defaultReps:15,unit:'reps',info:'Debout, légère flexion du coude. Monte les bras sur les côtés jusqu\'à l\'horizontale. Deltoïdes latéraux. Descente lente 3 sec.'},
  {id:'l_elev_front_halt',group:'epaules',name:'Élévation frontale haltères',equipment:'Haltères',defaultSets:3,defaultReps:12,unit:'reps',info:'Monte les bras devant jusqu\'à l\'horizontale. Prise pronation. Peut s\'alterner pour un meilleur contrôle. Deltoïdes antérieurs.'},
  {id:'l_oiseau_halt',group:'epaules',name:'Oiseau haltères penché',equipment:'Haltères',defaultSets:3,defaultReps:12,unit:'reps',info:'Buste penché à 45° ou horizontal. Ouvre les bras en arc de cercle vers l\'extérieur. Deltoïdes postérieurs et rhomboïdes.'},
  {id:'l_press_halt_assis',group:'epaules',name:'Développé épaules haltères assis',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Assis, dos droit. Haltères à hauteur des épaules, coudes à 90°. Pousse verticalement au-dessus de la tête. Descente contrôlée.'},
  // Pecs haltères
  {id:'l_floor_press_halt',group:'pecs',name:'Floor press haltères',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Allongé au sol, haltères à deux mains. Coudes à 45°. Pousse vers le plafond. Le sol limite l\'amplitude et protège les épaules.'},
  {id:'l_floor_press_halt_uni',group:'pecs',name:'Floor press haltères unilatéral',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Même position mais un bras à la fois. L\'autre bras stabilise. Travail antirotation du core. 10 reps de chaque côté.'},
  {id:'l_fly_halt_sol',group:'pecs',name:'Fly haltères au sol',equipment:'Haltères',defaultSets:3,defaultReps:12,unit:'reps',info:'Allongé au sol, bras légèrement fléchis. Ouvre les bras vers les côtés jusqu\'au sol, referme en arc. Pectoraux et deltoïdes antérieurs.'},
  // Dos haltères
  {id:'l_rowing_halt_uni',group:'dos',name:'Rowing haltère unilatéral',equipment:'Haltères',defaultSets:3,defaultReps:10,unit:'reps',info:'Un genou et une main sur un plan stable. Tire le coude vers la hanche en gardant le dos droit. Grand dorsal et rhomboïdes. 10 reps de chaque côté.'},
  {id:'l_pullover_halt',group:'dos',name:'Pull-over haltère au sol',equipment:'Haltères',defaultSets:3,defaultReps:12,unit:'reps',info:'Allongé au sol, haltère à deux mains. Bras tendus, descends derrière la tête jusqu\'au sol. Grand dorsal et dentelé antérieur.'}
];

const LIB_GROUPS=['dos','epaules','biceps','triceps','pecs','core','jambes','fessiers','mobilite'];

// ══ MUSCLE GROUPS ══
const DEFAULT_RECOVERY={dos:72,dos_epaules:72,pecs_triceps:72,jambes_fessiers:72,biceps_isole:48};
const LINKED_GROUPS={'dos':['dos_epaules'],'dos_epaules':['dos']};
// Liens partiels croisés : dos/dos_epaules <-> pecs_triceps et biceps_isole (48h), jambes_fessiers isolé
const LINKED_GROUPS_PARTIAL={'dos':{groups:['pecs_triceps','biceps_isole'],maxRecovery:48},'dos_epaules':{groups:['pecs_triceps','biceps_isole'],maxRecovery:48},'pecs_triceps':{groups:['dos_epaules','dos'],maxRecovery:48},'biceps_isole':{groups:['dos','dos_epaules'],maxRecovery:48}};

const MUSCLE_GROUPS=[
  {id:'dos',name:'Dos',icon:'🔙',color:'#5a9abf',
    warmup:[{id:'w_dos_rot',name:'Rotation externe élastique',sets:3,reps:15,unit:'reps',info:'Bras collé au corps, coude à 90°. Tire vers l\'extérieur. OBLIGATOIRE avant toute séance dos.',equipment:'Élastique'},{id:'w_dos_hang',name:'Dead hang passif',sets:2,reps:30,unit:'sec',info:'Suspension complète. Décompresse la colonne avant l\'effort.',equipment:'Chaise romaine'}],
    exercises:[
      {id:'dos_dead_hang',name:'Dead hang actif',sets:3,reps:20,unit:'sec',info:'Suspendu à la barre, pousse les omoplates vers le bas. Actif, pas passif.',equipment:'Chaise romaine'},
      {id:'dos_traction_neg',name:'Tractions négatives',sets:4,reps:5,unit:'reps',info:'Monte avec un saut, descends LENTEMENT en 5 secondes.',equipment:'Chaise romaine'},
      {id:'dos_traction_e',name:'Tractions élastique prise serrée',sets:3,reps:5,unit:'reps',info:'Contracte les omoplates AVANT de tirer. Montée explosive, descente 3 sec.',equipment:'Chaise romaine + Élastique'},
      {id:'dos_traction_large',name:'Tractions prise large',sets:3,reps:5,unit:'reps',info:'Mains à largeur épaules +20cm. Tire les coudes vers le bas et l\'extérieur.',equipment:'Chaise romaine + Élastique'},
      {id:'dos_rowing_kb',name:'Rowing KB unilatéral',sets:3,reps:10,unit:'reps',info:'Genou et main opposée appuyés sur une surface stable. Grand dorsal et rhomboïdes.',equipment:'Kettlebell'},
      {id:'dos_rowing_e',name:'Rowing élastique buste penché',sets:3,reps:12,unit:'reps',info:'Buste à 45°. Tire les coudes vers les hanches.',equipment:'Élastique'},
      {id:'dos_face_pull',name:'Face pull élastique',sets:3,reps:15,unit:'reps',info:'Élastique à hauteur du visage. Tire vers le front. Anti-voutement obligatoire.',equipment:'Élastique'},
      {id:'dos_ext',name:'Extensions dorsales',sets:3,reps:12,unit:'reps',info:'Chaise romaine. Descends le buste, remonte jusqu\'à l\'horizontale.',equipment:'Chaise romaine'},
      {id:'dos_towel',name:'Towel hang — grip',sets:3,reps:20,unit:'sec',info:'Serviette pliée sur la barre. Force la prise des doigts.',equipment:'Chaise romaine'},
      {id:'dos_bird_dog',name:'Bird dog (maintien 3s)',sets:3,reps:10,unit:'reps',info:'À 4 pattes. Étends bras droit + jambe gauche. Dos plat. MAINTIENS 3 sec.',equipment:''},
      {id:'dos_dead_bug',name:'Dead bug (maintien 2s)',sets:3,reps:8,unit:'reps',info:'Bras au plafond, genoux à 90°. Descends bras et jambe opposés. Dos plaqué. MAINTIENS 2 sec.',equipment:''},
      {id:'dos_rowing_halt',name:'Rowing haltère unilatéral',sets:3,reps:10,unit:'reps',info:'Un genou et une main sur un plan stable. Tire le coude vers la hanche. Grand dorsal et rhomboïdes. 10 reps de chaque côté.',equipment:'Haltères'},
      {id:'dos_pullover_halt',name:'Pull-over haltère au sol',sets:3,reps:12,unit:'reps',info:'Allongé au sol, haltère à deux mains. Descends derrière la tête jusqu\'au sol. Grand dorsal et dentelé.',equipment:'Haltères'}
    ],
    stretches:[{name:'Étirement grand dorsal',info:'Bras tendu accroché à la barre, genoux fléchis. 3 × 30 sec de chaque côté.'},{name:'Étirement trapèze',info:'Incline la tête sur le côté, oreille vers l\'épaule. 2 × 30 sec de chaque côté.'},{name:'Cat-cow',info:'À 4 pattes. Inspiration = dos en creux, expiration = dos en rond. 2 × 12 répétitions lentes.'}]
  },
  {id:'dos_epaules',name:'Dos + Épaules',icon:'🏋️',color:'#4a8abf',
    warmup:[{id:'w_rot_ext1',name:'Rotation externe élastique',sets:3,reps:15,unit:'reps',info:'Bras collé au corps, coude à 90°. Tire vers l\'extérieur lentement.',equipment:'Élastique'}],
    exercises:[
      {id:'dead_hang',name:'Dead hang actif',sets:3,reps:20,unit:'sec',info:'Suspendu à la barre, omoplates vers le bas.',equipment:'Chaise romaine'},
      {id:'tractions_e1',name:'Tractions élastique',sets:3,reps:5,unit:'reps',info:'Contracte les omoplates AVANT de tirer. Descente contrôlée 3 sec.',equipment:'Chaise romaine + Élastique'},
      {id:'tractions_n1',name:'Tractions négatives',sets:3,reps:5,unit:'reps',info:'Monte avec un saut, descends LENTEMENT en 5 secondes.',equipment:'Chaise romaine'},
      {id:'face_pull1',name:'Face pull élastique',sets:3,reps:15,unit:'reps',info:'Tire vers le front en ouvrant les coudes. Anti-voutement.',equipment:'Élastique'},
      {id:'rowing_e1',name:'Rowing élastique',sets:3,reps:12,unit:'reps',info:'Tire vers le ventre, coudes serrés.',equipment:'Élastique'},
      {id:'ytw1',name:'Y-T-W au sol (maintien 2s)',sets:3,reps:10,unit:'reps',info:'Y=bras en V, T=bras perpendiculaires, W=coudes à 90°. MAINTIENS 2 sec.',equipment:''},
      {id:'oiseau1',name:'Oiseau élastique',sets:3,reps:12,unit:'reps',info:'Buste légèrement penché, ouvre les bras en arc de cercle. Deltoïdes postérieurs.',equipment:'Élastique'},
      {id:'shrug1',name:'Shrug kettlebell',sets:3,reps:12,unit:'reps',info:'Hausse les épaules vers les oreilles, maintiens 1 sec. Trapèzes.',equipment:'Kettlebell'},
      {id:'dead_bug1',name:'Dead bug (maintien 2s)',sets:3,reps:8,unit:'reps',info:'Bras au plafond, genoux à 90°. MAINTIENS 2 sec.',equipment:''},
      {id:'bird_dog1',name:'Bird dog (maintien 3s)',sets:3,reps:10,unit:'reps',info:'À 4 pattes. Dos plat. MAINTIENS 3 sec.',equipment:''},
      {id:'elev_lat_halt1',name:'Élévation latérale haltères',sets:3,reps:15,unit:'reps',info:'Debout, légère flexion du coude. Monte les bras sur les côtés jusqu\'à l\'horizontale. Deltoïdes latéraux.',equipment:'Haltères'},
      {id:'oiseau_halt1',name:'Oiseau haltères penché',sets:3,reps:12,unit:'reps',info:'Buste penché à 45°. Ouvre les bras en arc de cercle vers l\'extérieur. Deltoïdes postérieurs.',equipment:'Haltères'}
    ],
    stretches:[{name:'Étirement grand dorsal',info:'Bras tendu accroché à la barre. 3 × 30 sec de chaque côté.'},{name:'Étirement épaule postérieure',info:'Bras croisé devant la poitrine. L\'autre bras tire le coude. 2 × 30 sec de chaque côté.'}]
  },
  {id:'pecs_triceps',name:'Pectoraux + Triceps',icon:'🤜',color:'#bf4a4a',
    warmup:[{id:'w_rot_ext3',name:'Rotation externe élastique',sets:3,reps:15,unit:'reps',info:'OBLIGATOIRE avant les pecs. Prépare les épaules au travail de poussée.',equipment:'Élastique'}],
    exercises:[
      {id:'pompes_incl2',name:'Pompes inclinées',sets:3,reps:10,unit:'reps',info:'Mains sur la chaise (60-70cm). Descente LENTE 4 sec, pause 1 sec, remontée explosive.',equipment:'Chaise romaine'},
      {id:'pompes_class2',name:'Pompes classiques',sets:3,reps:10,unit:'reps',info:'Corps en planche rigide. Descente 4 sec, pause 1 sec, remontée explosive.',equipment:''},
      {id:'pompes_pieds2',name:'Pompes pieds surélevés',sets:3,reps:8,unit:'reps',info:'Pieds sur la chaise. Max 70cm. Pectoraux supérieurs.',equipment:'Chaise romaine'},
      {id:'pompes_diam2',name:'Pompes diamant',sets:3,reps:8,unit:'reps',info:'Mains formant un losange. Coudes serrés.',equipment:''},
      {id:'dips2',name:'Dips chaise romaine',sets:3,reps:8,unit:'reps',info:'Coudes serrés. Descente jusqu\'à 90°.',equipment:'Chaise romaine'},
      {id:'ext_triceps2',name:'Extensions triceps kettlebell',sets:3,reps:10,unit:'reps',info:'KB à deux mains derrière la nuque, coudes près des oreilles.',equipment:'Kettlebell'},
      {id:'kickback2',name:'Kickback triceps élastique',sets:3,reps:12,unit:'reps',info:'Buste à 45°. Coude fixe. Étends le bras vers l\'arrière.',equipment:'Élastique'},
      {id:'face_pull3',name:'Face pull élastique (finisher obligatoire)',sets:3,reps:15,unit:'reps',info:'OBLIGATOIRE après les pecs. Contrebalance le travail de poussée.',equipment:'Élastique'},
      {id:'dead_bug3',name:'Dead bug (maintien 2s)',sets:3,reps:8,unit:'reps',info:'Bras au plafond. MAINTIENS 2 sec.',equipment:''},
      {id:'gainage_lat2',name:'Gainage latéral',sets:3,reps:30,unit:'sec',info:'Corps en ligne droite. 30 sec de chaque côté.',equipment:''},
      {id:'floor_press_halt2',name:'Floor press haltères',sets:3,reps:10,unit:'reps',info:'Allongé au sol, haltères. Coudes à 45°. Le sol limite l\'amplitude et protège les épaules.',equipment:'Haltères'},
      {id:'fly_halt_sol2',name:'Fly haltères au sol',sets:3,reps:12,unit:'reps',info:'Allongé au sol, bras légèrement fléchis. Ouvre les bras vers les côtés, referme en arc. Pectoraux.',equipment:'Haltères'}
    ],
    stretches:[{name:'Étirement pectoraux — cadre de porte',info:'Bras en L dans le cadre. 3 hauteurs. 45 secondes chaque position.'},{name:'Étirement triceps',info:'Bras plié derrière la tête. 2 × 30 sec de chaque côté.'}]
  },
  {id:'jambes_fessiers',name:'Jambes + Fessiers',icon:'🦵',color:'#4abf6a',
    warmup:[{id:'w_rot_bassin',name:'Rotation de bassin',sets:2,reps:10,unit:'reps',info:'Mains sur les hanches. Grands cercles. 10 dans chaque sens.',equipment:''},{id:'w_fentes_stat',name:'Fentes statiques',sets:2,reps:8,unit:'reps',info:'Grand pas en avant. Genou avant à 90°. 8 de chaque jambe.',equipment:''}],
    exercises:[
      {id:'hip_thrust2',name:'Hip thrust kettlebell',sets:4,reps:12,unit:'reps',info:'Dos sur surface stable, KB sur le bassin. CONTRACTE fessiers 2 sec en haut.',equipment:'Kettlebell'},
      {id:'pont_uni2',name:'Pont fessier unilatéral',sets:3,reps:12,unit:'reps',info:'Sur le dos, une jambe tendue. Contracte fort en haut. 12 de chaque jambe.',equipment:''},
      {id:'goblet2',name:'Goblet squat kettlebell',sets:3,reps:10,unit:'reps',info:'KB contre la poitrine. Descends LENTEMENT (3 sec), pause 2 sec en bas.',equipment:'Kettlebell'},
      {id:'bulgare2',name:'Squat bulgare chaise romaine',sets:3,reps:8,unit:'reps',info:'Pied arrière sur la chaise. Genou avant à 90°. 8 de chaque jambe.',equipment:'Chaise romaine'},
      {id:'fentes_m2',name:'Fentes marchées',sets:3,reps:12,unit:'reps',info:'En marchant, alterne les fentes. 12 de chaque jambe.',equipment:''},
      {id:'donkey2',name:'Donkey kicks',sets:3,reps:15,unit:'reps',info:'À 4 pattes. Pousse la jambe vers le haut. Maintiens 1 sec. 15 de chaque jambe.',equipment:''},
      {id:'clamshells2',name:'Clamshells',sets:3,reps:15,unit:'reps',info:'Sur le côté. Ouvre le genou vers le plafond. Fessier moyen.',equipment:''},
      {id:'swing2',name:'Swing kettlebell',sets:3,reps:20,unit:'reps',info:'Propulse avec les hanches. La force vient des fessiers.',equipment:'Kettlebell'},
      {id:'step_up2',name:'Step up chaise romaine',sets:3,reps:10,unit:'reps',info:'Pose le pied sur la chaise. Monte sur le TALON. 10 de chaque jambe.',equipment:'Chaise romaine'},
      {id:'dead_bug4',name:'Dead bug (maintien 2s)',sets:3,reps:8,unit:'reps',info:'Bras au plafond. Dos plaqué. MAINTIENS 2 sec.',equipment:''},
      {id:'bird_dog4',name:'Bird dog (maintien 3s)',sets:3,reps:10,unit:'reps',info:'Dos plat. MAINTIENS 3 sec.',equipment:''},
      {id:'mollets_j1',name:'Élévation mollets debout',sets:4,reps:20,unit:'reps',info:'Maintiens 1 sec en haut. Descends LENTEMENT.',equipment:'Kettlebell'},
      {id:'mollets_j2',name:'Élévation mollets unilatérale',sets:3,reps:15,unit:'reps',info:'Une jambe à la fois. Amplitude complète.',equipment:'Chaise romaine'}
    ],
    stretches:[{name:'Étirement fessiers — pigeon',info:'Position du pigeon. Jambe avant en croix. 3 × 45 sec de chaque côté.'},{name:'Étirement quadriceps',info:'Talon vers les fesses. 2 × 30 sec de chaque côté.'},{name:'Étirement fléchisseurs de hanche',info:'Fente basse, genou arrière au sol. ESSENTIEL conducteurs. 2 × 30 sec de chaque côté.'}]
  },
  {id:'biceps_isole',name:'Biceps isolé',icon:'🎯',color:'#bf9a4a',
    warmup:[{id:'w_rot_poignets',name:'Rotations de poignets',sets:2,reps:15,unit:'reps',info:'Bras tendus. Rotate les poignets dans les deux sens. 15 dans chaque sens.',equipment:''}],
    exercises:[
      {id:'curl_b_i',name:'Curl biceps kettlebell',sets:4,reps:10,unit:'reps',info:'Paume vers le HAUT. Montée explosive, descente 3 secondes.',equipment:'Kettlebell'},
      {id:'curl_m_i',name:'Curl marteau kettlebell',sets:4,reps:10,unit:'reps',info:'Prise neutre. 2 sec montée, 3 sec descente.',equipment:'Kettlebell'},
      {id:'curl_inc_i',name:'Curl incliné élastique',sets:3,reps:12,unit:'reps',info:'Élastique fixé bas. Meilleure amplitude.',equipment:'Élastique'},
      {id:'curl_con_i',name:'Curl concentré kettlebell',sets:3,reps:10,unit:'reps',info:'Coude contre le genou. 10 de chaque bras.',equipment:'Kettlebell'},
      {id:'curl_21_i',name:'Curl 21s kettlebell',sets:2,reps:21,unit:'reps',info:'7 reps demi-bas + 7 demi-haut + 7 amplitude complète.',equipment:'Kettlebell'},
      {id:'curl_iso_i',name:'Curl isométrique (tenu)',sets:2,reps:30,unit:'sec',info:'Coude à 90°. Tiens SANS BOUGER 30 secondes.',equipment:'Kettlebell'},
      {id:'dead_bug5',name:'Dead bug (maintien 2s)',sets:3,reps:8,unit:'reps',info:'Core. MAINTIENS 2 sec.',equipment:''},
      {id:'curl_halt_alt_i',name:'Curl haltères alterné debout',sets:4,reps:10,unit:'reps',info:'Alterne bras gauche et droit. Coude fixe. Montée explosive, descente 3 sec.',equipment:'Haltères'},
      {id:'curl_halt_marteau_i',name:'Curl haltères marteau alterné',sets:3,reps:10,unit:'reps',info:'Prise neutre (pouce vers le haut). Alterne gauche droite. Brachial et long supinateur.',equipment:'Haltères'},
      {id:'curl_halt_incl_i',name:'Curl haltères incliné',sets:3,reps:10,unit:'reps',info:'Assis incliné à 60°. Bras pendants derrière le corps. Étirement maximal du biceps long.',equipment:'Haltères'}
    ],
    stretches:[{name:'Étirement biceps',info:'Bras tendu en arrière, paume vers le haut, pouce vers le bas. 3 × 30 sec de chaque côté.'}]
  }
];

const GROUP_NAMES_FR={dos:'Dos',epaules:'Épaules',biceps:'Biceps',triceps:'Triceps',pecs:'Pectoraux',core:'Core',jambes:'Jambes',fessiers:'Fessiers',mollets:'Mollets',mobilite:'Mobilité'};

// ══ RECUP ACTIVITIES ══
const GROUP_BODYPARTS={
  'dos':['dos','epaules'],'dos_epaules':['dos','epaules'],
  'pecs_triceps':['pecs','triceps'],'jambes_fessiers':['jambes','fessiers'],'biceps_isole':['biceps']
};
const RECUP_ACTIVITIES=[
  {id:'yoga',    name:'🧘 Yoga doux',         duration:'20–30 min',benefit:'Détente du système nerveux, réduction du cortisol. Aucune contre-indication, indiquée quelle que soit la fatigue.',solicits:[]},
  {id:'stretch', name:'🤸 Stretching',        duration:'15–20 min',benefit:'Réduction des DOMS, maintien de l\'amplitude articulaire. Toujours bénéfique.',solicits:[]},
  {id:'marche',  name:'🚶 Marche',            duration:'30–45 min',benefit:'Active la circulation sanguine, élimine les métabolites musculaires. Légère sur les jambes.',solicits:['jambes','fessiers']},
  {id:'mobilite',name:'🦵 Mobilité hanche',   duration:'20 min',   benefit:'Mobilité hanche et lombaires, essentielle pour les conducteurs. Sollicite légèrement jambes et fessiers.',solicits:['jambes','fessiers']},
  {id:'natcrawl',name:'🏊 Natation crawl/dos',duration:'30–45 min',benefit:'Cardio faible impact, décharge articulaire complète. Sollicite dos, épaules et biceps.',solicits:['dos','epaules','biceps']},
  {id:'natbrasse',name:'🏊 Natation brasse',  duration:'30–45 min',benefit:'Cardio complet et symétrique. Sollicite pectoraux, triceps et jambes.',solicits:['pecs','triceps','jambes']},
  {id:'velo',    name:'🚴 Vélo doux',         duration:'30–45 min',benefit:'Cardio sans impact, favorise la récupération active. Sollicite jambes et fessiers.',solicits:['jambes','fessiers']}
];

// ══ RECUP LIBRARY ══
const RECUP_LIBRARY=[
// ─── YOGA ───
{id:'ry_montagne',cat:'yoga',name:'Montagne (Tadasana)',icon:'🧘',duration:30,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','pré-sommeil','conducteur'],info:'Debout, pieds joints ou léger écart, poids équilibré sur les deux pieds. Ancres les 4 coins des pieds au sol. Remonte l\'énergie depuis les pieds : genoux légèrement actifs, quadriceps engagés, bassin neutre, sternum vers le haut, épaules relâchées, sommet du crâne vers le ciel. Respiration lente et profonde. Posture de base qui aligne toute la colonne et entraîne la conscience corporelle.'},
{id:'ry_chaise',cat:'yoga',name:'Chaise (Utkatasana)',icon:'🧘',duration:30,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','post-sport'],info:'Depuis Tadasana, plie les genoux comme pour t\'asseoir sur une chaise imaginaire. Bras au-dessus de la tête, regard vers l\'avant ou légèrement vers le haut. Genoux dans l\'axe des orteils, poids sur les talons. Renforce quadriceps, fessiers, érecteurs du rachis. Tiens 30 sec en respirant régulièrement.'},
{id:'ry_arbre',cat:'yoga',name:'Arbre (Vrikshasana)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['réveil','conducteur'],info:'Sur un pied, l\'autre pied contre la cheville, le tibia ou la cuisse (jamais le genou). Mains en prière ou bras au ciel. Fixe un point devant toi. Renforce la cheville, améliore l\'équilibre proprioceptif. 30 sec par côté. Très utile pour les conducteurs qui ont perdu la sensibilité proprioceptive.'},
{id:'ry_guerrier1',cat:'yoga',name:'Guerrier I (Virabhadrasana I)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport','réveil'],info:'Fente avant, pied arrière à 45°, genou avant à 90°. Hanches de face. Bras au ciel, regard vers le haut. Étire puissamment le hip flexor de la jambe arrière, renforce quadriceps et fessiers. Ouverture thoracique. 30 sec par côté.'},
{id:'ry_guerrier2',cat:'yoga',name:'Guerrier II (Virabhadrasana II)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport','conducteur'],info:'Fente latérale, pied arrière perpendiculaire, bras en croix au-delà des deux pieds, regard sur la main avant. Hanches ouvertes sur le côté. Renforce cuisses, fessiers, améliore l\'équilibre. Excellent pour les conducteurs. 30 sec par côté.'},
{id:'ry_guerrier3',cat:'yoga',name:'Guerrier III (Virabhadrasana III)',icon:'🧘',duration:20,unit:'sec',bilateral:true,level:'intermédiaire',tags:['post-sport'],info:'Sur une jambe, buste et jambe arrière horizontaux, bras vers l\'avant ou sur les hanches. Corps en T. Renforce la chaîne postérieure complète (ischio, fessier, érecteurs), proprioception intense. 20 sec par côté. Progression : commencer avec les mains au mur.'},
{id:'ry_deesse',cat:'yoga',name:'Déesse (Utkata Konasana)',icon:'🧘',duration:30,unit:'sec',bilateral:false,level:'débutant',tags:['conducteur','post-sport'],info:'Jambes très écartées, pieds pointés à 45°, genoux pliés à 90° vers l\'extérieur. Bras en cactus (coudes à 90°). Ouverture profonde des hanches, adducteurs, pecs et épaules. 30 sec. Idéal pour les hanches serrées de la position assise.'},
{id:'ry_aigle',cat:'yoga',name:'Aigle (Garudasana)',icon:'🧘',duration:20,unit:'sec',bilateral:true,level:'intermédiaire',tags:['post-sport','conducteur'],info:'Sur un pied, genou légèrement plié. Enroule la jambe libre autour. Bras enroulés (avant-bras croisés, paumes jointes si possible). Coudes à hauteur des yeux. Étire profondément les épaules et le haut du dos, ouvre les hanches. 20 sec par côté.'},
{id:'ry_demi_lune',cat:'yoga',name:'Demi-lune (Ardha Chandrasana)',icon:'🧘',duration:20,unit:'sec',bilateral:true,level:'intermédiaire',tags:['post-sport'],info:'Sur une jambe, buste penché latéralement, jambe arrière horizontale, bras vers le plafond. Corps dans un plan latéral. Renforce la hanche, ischio, mobilité thoracique. Main au sol ou sur un bloc. 20 sec par côté.'},
{id:'ry_flex_debout',cat:'yoga',name:'Flexion avant debout (Uttanasana)',icon:'🧘',duration:45,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','pré-sommeil','anti-douleur dos'],info:'Debout, penche-toi en avant depuis les hanches, genoux légèrement fléchis si besoin. Laisse tomber la tête, attrape les coudes. Étire ischio-jambiers, bas du dos, décompresse la colonne par gravité. Effet calmant sur le système nerveux. 45 sec.'},
{id:'ry_fente_croissant',cat:'yoga',name:'Fente haute croissant (Anjaneyasana)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['réveil','conducteur','anti-douleur dos'],info:'Genou arrière au sol ou levé, pied avant à 90°. Bras au ciel, légère extension du dos vers l\'arrière. Hip flexor et quadriceps de la jambe arrière, ouverture de la cage thoracique. ESSENTIEL pour les conducteurs et les assis prolongés. 30 sec par côté.'},
{id:'ry_malasana',cat:'yoga',name:'Yogi squat (Malasana)',icon:'🧘',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['conducteur','réveil','post-sport'],info:'Squat profond, pieds légèrement écartés et à 45°, fesses vers le sol. Coudes contre les genoux pour les ouvrir. Mains en prière. Si les talons se lèvent : mettre un livre dessous. Hanches, chevilles, bas du dos. Posture naturelle humaine perdue avec les chaises.'},
{id:'ry_triangle',cat:'yoga',name:'Triangle (Trikonasana)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport','conducteur'],info:'Jambes très écartées, bras en croix. Incline le buste latéralement, main vers le pied ou le tibia, autre bras vers le plafond. Regard vers le haut. Ischio-jambiers, obliques et colonne. 30 sec par côté.'},
{id:'ry_enfant',cat:'yoga',name:'Enfant (Balasana)',icon:'🧘',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil','anti-douleur dos','réveil'],info:'Agenouillez-vous, gros orteils joints, genoux écartés à la largeur des hanches. Étirez les bras devant, front au sol. Étire bas du dos, hanches et épaules. Respiration abdominale profonde. Pose restauratrice par excellence. Idéale après séance dos ou avant dormir.'},
{id:'ry_chien',cat:'yoga',name:'Chien tête en bas (Adho Mukha)',icon:'🧘',duration:45,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','post-sport'],info:'Depuis la planche, pousse les hanches vers le plafond. Corps en V inversé. Talons vers le sol. Étire ischio-jambiers, mollets, épaules et décompresse la colonne. Point central de nombreuses séances. Tiens 45 sec en alternant les flexions de jambe pour approfondir.'},
{id:'ry_pigeon',cat:'yoga',name:'Pigeon couché (Supta Kapotasana)',icon:'🧘',duration:60,unit:'sec',bilateral:true,level:'débutant',tags:['pré-sommeil','conducteur','anti-douleur dos'],info:'Sur le dos. Croise la cheville droite sur le genou gauche (figure 4). Tire la cuisse gauche vers toi. Fessier profond et piriforme. Essentiel contre douleurs lombaires et sciatiques. Version douce sans risque pour le genou. 60 sec par côté.'},
{id:'ry_torsion',cat:'yoga',name:'Torsion allongée (Supta Matsyendrasana)',icon:'🧘',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['pré-sommeil','anti-douleur dos','réveil'],info:'Sur le dos. Genou fléchi bascule vers le côté opposé. Bras en croix, regard à l\'opposé. Décompresse lombaires et vertèbres thoraciques. Stretch des obliques et des spinaux. Idéal avant dormir. 45 sec par côté.'},
{id:'ry_cat_cow',cat:'yoga',name:'Chat-Vache (Marjaryasana-Bitilasana)',icon:'🧘',duration:60,unit:'sec',reps:12,bilateral:false,level:'débutant',tags:['réveil','anti-douleur dos','conducteur'],info:'À 4 pattes, poignets sous épaules, genoux sous hanches. Inspiration : dos en creux, tête et coccyx vers le haut (vache). Expiration : dos arrondi, menton vers poitrine (chat). 12 reps lentes. Mobilise toute la colonne vertèbre par vertèbre. Soulagement immédiat des raideurs.'},
{id:'ry_cobra',cat:'yoga',name:'Cobra / Sphinx',icon:'🧘',duration:45,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','anti-douleur dos'],info:'Allongé ventre au sol. Sphinx : avant-bras au sol, buste soulevé (version douce, idéale débutant). Cobra : mains sous les épaules, buste soulevé plus haut. Garde les hanches au sol. Ouvre pectoraux, étire abdominaux et lombaires. Contre-posture après flexion.'},
{id:'ry_papillon',cat:'yoga',name:'Papillon assis (Baddha Konasana)',icon:'🧘',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil','conducteur'],info:'Assis, plantes des pieds jointes, genoux ouverts. Penche-toi en avant avec le dos droit. Adducteurs et hanches internes. Coussins sous les genoux si tensions. Très efficace pour les conducteurs et les assis prolongés. Variante yin : laisse tomber passivement.'},
{id:'ry_jambes_mur',cat:'yoga',name:'Jambes au mur (Viparita Karani)',icon:'🧘',duration:120,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil','post-sport'],info:'Allongé sur le dos, jambes verticales contre un mur, fesses proches du mur. Favorise le retour veineux, réduit les oedèmes des membres inférieurs. Effet calmant sur le système nerveux (nerf vague). Excellent après séance jambes ou longue journée. Pose restauratrice. 2 à 5 minutes.'},
{id:'ry_fente_basse',cat:'yoga',name:'Fente basse (Anjaneyasana basse)',icon:'🧘',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['conducteur','anti-douleur dos','post-sport'],info:'Genou arrière au sol, pied avant à 90°. Hanches poussées vers le bas et l\'avant. Variante : bras au ciel pour étirement complet. Hip flexor et quadriceps de la jambe arrière. CRITIQUE après position assise prolongée (conducteurs). 45 sec par côté.'},
{id:'ry_happy_baby',cat:'yoga',name:'Happy Baby (Ananda Balasana)',icon:'🧘',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil','anti-douleur dos'],info:'Sur le dos, genoux vers les aisselles. Attrape les bords extérieurs des pieds. Berce doucement de gauche à droite. Décomprime les lombaires, ouvre hanches et fessiers. Très relaxant, idéal en fin de séance ou avant dormir.'},
{id:'ry_savasana',cat:'yoga',name:'Savasana (relaxation totale)',icon:'🧘',duration:180,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil'],info:'Allongé sur le dos, membres légèrement écartés, paumes vers le haut. Yeux fermés. Relâchement progressif de chaque partie du corps. Aussi importante que les postures actives — c\'est là que le corps intègre les bénéfices. Minimum 3 minutes. Ne pas zapper cette posture.'},
{id:'ry_bridge',cat:'yoga',name:'Pont de yoga (Setu Bandhasana)',icon:'🧘',duration:30,unit:'sec',reps:10,bilateral:false,level:'débutant',tags:['réveil','post-sport'],info:'Sur le dos, genoux fléchis, pieds à plat. Soulève les hanches en contractant fessiers et abdominaux. Option A : maintiens 30 sec. Option B : 10 répétitions lentes (3 sec monte, 3 sec descend). Renforce fessiers et ischio, ouvre pectoraux et hip flexors.'},
{id:'ry_bateau',cat:'yoga',name:'Bateau (Navasana)',icon:'🧘',duration:20,unit:'sec',reps:5,bilateral:false,level:'intermédiaire',tags:['post-sport'],info:'Assis, jambes à 45°, bras parallèles au sol. Corps en V. Renforce puissamment le core, hip flexors et érecteurs. 5 répétitions × 20 sec. Variante douce : jambes fléchies, mains sur les cuisses. Améliore la stabilité de la colonne.'},
{id:'ry_sauterelle',cat:'yoga',name:'Sauterelle (Salabhasana)',icon:'🧘',duration:20,unit:'sec',reps:5,bilateral:false,level:'débutant',tags:['anti-douleur dos','réveil'],info:'Allongé ventre au sol, bras le long du corps. Soulève simultanément tête, bras et jambes. Maintiens 20 sec. 5 reps. Renforce toute la chaîne postérieure (érecteurs, ischio, fessiers, trapèzes). Excellent contre le mal de dos chronique. Pas de douleur : arrêter si gêne dans les lombaires.'},
{id:'ry_chameau',cat:'yoga',name:'Chameau (Ustrasana)',icon:'🧘',duration:20,unit:'sec',bilateral:false,level:'intermédiaire',tags:['anti-douleur dos','post-sport'],info:'À genoux, hanches dans l\'axe des genoux. Pose les mains sur les talons (ou sur les lombaires pour la version douce). Ouvre la cage thoracique vers le ciel. Extension dorsale profonde, ouverture des pectoraux et des hip flexors. Contre-posture après position voûtée. 20 sec × 3.'},
{id:'ry_pince',cat:'yoga',name:'Pince assise (Paschimottanasana)',icon:'🧘',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil','post-sport','anti-douleur dos'],info:'Assis, jambes tendues devant. Penche-toi en avant depuis les hanches (pas en arrondissant le dos). Attrape les pieds, chevilles ou tibia selon ta souplesse. Ischio-jambiers, bas du dos, mollets. Effet parasympathique fort. 60 sec de relâchement progressif à chaque expiration.'},
{id:'ry_tete_genou',cat:'yoga',name:'Tête au genou (Janu Sirsasana)',icon:'🧘',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport','pré-sommeil'],info:'Assis, un genou plié (pied contre l\'aine), l\'autre jambe tendue. Penche vers la jambe tendue. Ischio-jambiers et bas du dos d\'un côté. Plus accessible que la pince. 45 sec par côté. Ne force pas : relâche progressivement à chaque expiration.'},
{id:'ry_torsion_assise',cat:'yoga',name:'Torsion assise (Marichyasana)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['réveil','anti-douleur dos'],info:'Assis, un genou plié pied au sol. Torsion du buste vers ce côté, bras opposé contre le genou pour levier. Regard par-dessus l\'épaule. Mobilité thoracique et lombaire, massage des organes. 30 sec par côté.'},
{id:'ry_demi_pigeon',cat:'yoga',name:'Demi-pigeon complet (Ardha Kapotasana)',icon:'🧘',duration:60,unit:'sec',bilateral:true,level:'intermédiaire',tags:['conducteur','anti-douleur dos','pré-sommeil'],info:'Jambe avant pliée à 90° devant, jambe arrière tendue. Descends le buste vers l\'avant, front au sol ou sur les bras. Piriforme, fessier profond, hip flexor arrière. Version yin profonde. 60 sec par côté. Si douleur au genou : utiliser la version sur le dos (pigeon couché).'},
{id:'ry_grenouille',cat:'yoga',name:'Grenouille (Mandukasana)',icon:'🧘',duration:60,unit:'sec',bilateral:false,level:'intermédiaire',tags:['conducteur','post-sport'],info:'À 4 pattes. Écarte les genoux le maximum, pieds pointant vers l\'extérieur, chevilles dans l\'axe des genoux. Descends sur les avant-bras. Adducteurs profonds et rotateurs de hanche. Tiens 60 sec en respirant profondément. Une des postures les plus efficaces pour les hanches serrées.'},
{id:'ry_etoile',cat:'yoga',name:'Étoile de mer (Starfish)',icon:'🧘',duration:120,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil'],info:'Sur le dos, bras et jambes légèrement écartés, paumes vers le haut. Corps en étoile. Relâchement total. Variante de Savasana plus ouverte. Excellent pour les épaules enroulées et les tensions thoraciques. 2 minutes minimum.'},
{id:'ry_baton',cat:'yoga',name:'Bâton (Dandasana)',icon:'🧘',duration:30,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','post-sport'],info:'Assis, jambes tendues devant, dos droit. Appuie les mains au sol à côté des hanches, doigts vers l\'avant. Pieds en flexion. Active le core pour maintenir le dos vertical. Renforce les érecteurs et améliore la conscience posturale. Base de toutes les postures assises.'},
{id:'ry_heron',cat:'yoga',name:'Héron (Krounchasana)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'intermédiaire',tags:['post-sport'],info:'Assis, une jambe fléchie sous toi, l\'autre tendue et soulevée à la verticale. Attrape le pied de la jambe tendue. Ischio-jambiers profonds et équilibre. 30 sec par côté. Version douce : jambe à 45° seulement. Progression vers la posture complète.'},
{id:'ry_mur_dos',cat:'yoga',name:'Dos au mur jambes fléchies',icon:'🧘',duration:90,unit:'sec',bilateral:false,level:'débutant',tags:['pré-sommeil','anti-douleur dos'],info:'Fesses contre le mur, jambes à 90° contre le mur (ou fléchies pieds au mur). Totale détente de la chaîne postérieure. Décompression lombaire passive. Idéale en fin de journée ou après position assise prolongée. Version encore plus restauratrice que jambes au mur.'},
{id:'ry_poisson',cat:'yoga',name:'Poisson (Matsyasana)',icon:'🧘',duration:30,unit:'sec',bilateral:false,level:'débutant',tags:['anti-douleur dos','réveil'],info:'Sur le dos, mains sous les fesses, coudes au sol. Soulève la cage thoracique, laisse tomber la tête en arrière (sommet du crâne au sol, doucement). Contre-étirement du cou, ouverture thoracique puissante. Contre-posture après postures en avant. 30 sec.'},
{id:'ry_janu',cat:'yoga',name:'Janu Sirsasana B (avancé)',icon:'🧘',duration:30,unit:'sec',bilateral:true,level:'avancé',tags:['post-sport'],info:'Comme la pince mais avec un genou très ouvert vers le côté (talon contre le périnée). Penche vers la jambe tendue. Adducteurs et ischio plus profonds. 30 sec par côté. Niveau avancé : ne force pas l\'ouverture.'},
// ─── STRETCHING ───
{id:'rs_ischio',cat:'stretch',name:'Ischio-jambiers allongé',icon:'🤸',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport','anti-douleur dos'],info:'Sur le dos. Soulève une jambe tendue en attrapant le mollet ou la cuisse. Dos plaqué au sol. Variante : pied contre le mur. 45 sec par côté. Essentiel après séance jambes. Ne jamais arrondir le dos pour atteindre le pied.'},
{id:'rs_quad',cat:'stretch',name:'Quadriceps debout',icon:'🤸',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport','conducteur'],info:'Debout, attrape le pied derrière la fesse. Genoux joints, hanches neutres (ne pas creuser le bas du dos). Appuie-toi sur un mur si besoin. 30 sec par côté. Indispensable après séance jambes ou après conduite prolongée.'},
{id:'rs_mollet',cat:'stretch',name:'Mollets — appui mural',icon:'🤸',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport'],info:'Face à un mur, une jambe en arrière tendue, talon au sol. Pousse le mur. Pour le soléaire : fléchis légèrement le genou arrière. 45 sec par côté. Après séance jambes ou longue marche. Prévient les contractures et les crampes nocturnes.'},
{id:'rs_pec',cat:'stretch',name:'Pectoraux — angle mural',icon:'🤸',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['anti-douleur dos','conducteur','post-sport'],info:'Bras à 90° en appui sur un montant (coude à hauteur d\'épaule). Tourne doucement le corps vers l\'opposé. Pectoraux et deltoïde antérieur. 45 sec par côté. Essentiel contre la cyphose et les épaules enroulées. À faire tous les jours si travail sur écran.'},
{id:'rs_grand_dorsal',cat:'stretch',name:'Grand dorsal — suspension',icon:'🤸',duration:45,unit:'sec',bilateral:false,level:'débutant',tags:['anti-douleur dos','post-sport'],info:'Tiens une barre ou un montant. Laisse le poids du corps tirer vers l\'arrière, genoux fléchis. Grand dorsal et colonne. Variante au sol : à genoux, bras tendu sur une surface, laisse tomber les épaules. 45 sec.'},
{id:'rs_trapeze',cat:'stretch',name:'Trapèze et cervicales',icon:'🤸',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['conducteur','anti-douleur dos','pré-sommeil'],info:'Assis ou debout. Incline doucement la tête sur le côté (oreille vers l\'épaule). Pose la main sur la tempe SANS tirer. Respiration lente. 30 sec par côté. Contre les tensions de nuque liées au stress, écran ou conduite prolongée.'},
{id:'rs_fessier4',cat:'stretch',name:'Fessier — figure 4',icon:'🤸',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['conducteur','post-sport','anti-douleur dos'],info:'Assis sur une chaise ou au sol. Croise la cheville sur le genou opposé. Penche légèrement le buste en avant. Piriforme et fessier profond. 45 sec par côté. Idéal post-séance jambes/fessiers ou après longue station assise.'},
{id:'rs_hip_flex',cat:'stretch',name:'Hip flexor — fente au sol',icon:'🤸',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['conducteur','anti-douleur dos'],info:'Genou arrière au sol, pied avant à 90°. Pousse les hanches en avant et vers le bas. Iliopsoas et droit antérieur. CRITIQUE après position assise prolongée. 45 sec par côté, respire en relâchant à chaque expiration.'},
{id:'rs_adducteurs',cat:'stretch',name:'Adducteurs — papillon passif',icon:'🤸',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['conducteur','pré-sommeil'],info:'Assis, plantes de pieds jointes. Laisse tomber les genoux vers le sol naturellement. Incline-toi légèrement en avant. Pour plus d\'intensité : appuie doucement sur les genoux. 60 sec. Adducteurs et hanches internes.'},
{id:'rs_epaule',cat:'stretch',name:'Épaule — croix devant',icon:'🤸',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport'],info:'Bras droit tendu en croix devant toi. Le bras gauche pousse l\'avant-bras droit vers le torse. Deltoïde postérieur et coiffe des rotateurs. 30 sec par côté. Indispensable après séance dos ou épaules.'},
{id:'rs_triceps',cat:'stretch',name:'Triceps — bras derrière nuque',icon:'🤸',duration:30,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport'],info:'Bras droit plié derrière la nuque, coude vers le plafond. La main gauche pousse doucement le coude vers le bas. Chef long du triceps. 30 sec par côté. Après séance dos, épaules ou bras.'},
{id:'rs_lombaires',cat:'stretch',name:'Lombaires — genoux poitrine',icon:'🤸',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['réveil','anti-douleur dos','pré-sommeil'],info:'Sur le dos. Ramène les deux genoux contre la poitrine. Berce doucement de gauche à droite. Lombaires et bas du dos. 60 sec. Recommandé chaque matin avant de se lever et après séance dos.'},
{id:'rs_itband',cat:'stretch',name:'Bandelette ilio-tibiale (TFL)',icon:'🤸',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['post-sport'],info:'Debout, croise la jambe droite derrière la gauche. Penche le buste vers la droite. Bandelette ilio-tibiale et TFL. 45 sec par côté. Essentiel pour prévenir les douleurs de genou chez les sportifs. À inclure après toute séance jambes.'},
{id:'rs_pec_sol',cat:'stretch',name:'Pectoraux — bras sol',icon:'🤸',duration:60,unit:'sec',bilateral:true,level:'débutant',tags:['pré-sommeil','anti-douleur dos'],info:'Allongé ventre au sol. Étends un bras à 90° sur le côté, paume vers le bas. Roule légèrement sur le côté pour intensifier. Pectoraux et avant-épaule. 60 sec par côté. Version très douce et restauratrice.'},
{id:'rs_psoas_sol',cat:'stretch',name:'Psoas — étirement profond',icon:'🤸',duration:60,unit:'sec',bilateral:true,level:'intermédiaire',tags:['conducteur','anti-douleur dos'],info:'Sur le dos, un genou contre la poitrine, l\'autre jambe tendue au sol. Maintiens fermement le genou. La jambe tendue s\'allonge activement. Psoas et iliaque profonds. 60 sec par côté. Plus efficace que la fente pour cibler le psoas pur. Incontournable pour les conducteurs.'},
{id:'rs_thoracique',cat:'stretch',name:'Ouverture thoracique — rouleau/sol',icon:'🤸',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['anti-douleur dos','conducteur'],info:'Assis face à une chaise ou au sol. Pose les coudes sur la surface, mains jointes. Laisse la tête descendre entre les bras, hanches vers l\'arrière. Triangle thoracique et grand dorsal. 60 sec. Contre la cyphose et les tensions inter-scapulaires.'},
// ─── MOBILITÉ HANCHES ───
{id:'rm_9090',cat:'mobilite',name:'90/90 — rotation des hanches',icon:'🦵',duration:45,unit:'sec',bilateral:true,level:'débutant',tags:['conducteur','post-sport'],info:'Assis au sol. Jambe avant à 90° (genou et cheville alignés). Jambe arrière à 90° sur le côté. Dos droit. Maintiens 45 sec par côté. Outil le plus complet pour travailler la rotation interne ET externe des hanches simultanément.'},
{id:'rm_cars',cat:'mobilite',name:'Hip CARs — rotations articulaires',icon:'🦵',duration:60,unit:'sec',reps:5,bilateral:true,level:'débutant',tags:['réveil','post-sport','conducteur'],info:'À 4 pattes. Genou vers la poitrine → vers le côté (90°) → jambe déployée vers l\'arrière → descend. Grand cercle lent et contrôlé. 5 reps par côté. Technique FRC (Functional Range Conditioning). Lubrifie l\'articulation coxo-fémorale. Idéal en échauffement ou réveil.'},
{id:'rm_deep_squat',cat:'mobilite',name:'Deep squat tenu',icon:'🦵',duration:60,unit:'sec',bilateral:false,level:'débutant',tags:['conducteur','réveil','post-sport'],info:'Squat profond, talons au sol, dos droit. Coudes contre les genoux pour les ouvrir. Si les talons se lèvent : mettre un livre dessous. Mobilise hanches, chevilles et thoracique. Posture naturelle humaine — à récupérer progressivement sur plusieurs semaines.'},
{id:'rm_frog',cat:'mobilite',name:'Frog stretch',icon:'🦵',duration:60,unit:'sec',bilateral:false,level:'intermédiaire',tags:['conducteur','post-sport'],info:'À 4 pattes. Écarte les genoux le maximum, pieds pointant vers l\'extérieur (chevilles dans l\'axe des genoux). Recule les hanches vers l\'arrière. Berce avant-arrière. Adducteurs profonds. Progression : descends la poitrine vers le sol sur les avant-bras.'},
{id:'rm_world',cat:'mobilite',name:'World\'s Greatest Stretch',icon:'🦵',duration:45,unit:'sec',reps:5,bilateral:true,level:'intermédiaire',tags:['réveil','post-sport'],info:'Fente avant. Main intérieure au sol. Bras extérieur vers le plafond (rotation thoracique). Reviens. Puis talon au sol, hanches vers le ciel. 5 répétitions fluides par côté. Combine hip flexor + rotation thoracique + ischio. L\'étirement le plus complet qui existe.'},
{id:'rm_cossack',cat:'mobilite',name:'Cossack squat',icon:'🦵',duration:45,unit:'sec',reps:8,bilateral:false,level:'intermédiaire',tags:['post-sport','conducteur'],info:'Jambes très écartées. Fléchis une jambe à fond (pied à plat), l\'autre reste tendue (pied en flexion vers le haut). Bascule d\'un côté à l\'autre. 8 reps lentes par côté. Adducteurs, hanches et mobilité de cheville.'},
{id:'rm_hip_circle',cat:'mobilite',name:'Cercles de hanches — quadrupède',icon:'🦵',duration:60,unit:'sec',reps:10,bilateral:true,level:'débutant',tags:['réveil','conducteur'],info:'À 4 pattes. Genou décollé. Trace un grand cercle avec la hanche : vers le coude → vers le côté → vers l\'arrière → descend. 10 reps dans chaque sens, chaque jambe. Lubrifie la capsule articulaire coxo-fémorale.'},
{id:'rm_lateral_lunge',cat:'mobilite',name:'Fente latérale active',icon:'🦵',duration:45,unit:'sec',reps:10,bilateral:false,level:'débutant',tags:['post-sport','conducteur'],info:'Grand pas sur le côté. Genou fléchi à 90°, pied à plat. L\'autre jambe tendue. Bascule d\'un côté à l\'autre en contrôlant. 10 reps par côté. Adducteurs et mobilité latérale des hanches.'},
{id:'rm_hip_rot',cat:'mobilite',name:'Hip flexor avec rotation',icon:'🦵',duration:45,unit:'sec',reps:8,bilateral:true,level:'intermédiaire',tags:['réveil','conducteur','post-sport'],info:'Fente basse, genou arrière au sol. Bras du côté avant vers le plafond avec rotation du torse. 8 rotations par côté. Combine étirement hip flexor + mobilité thoracique. Très complet pour les conducteurs.'},
{id:'rm_piriforme',cat:'mobilite',name:'Piriforme — étirement croisé',icon:'🦵',duration:60,unit:'sec',bilateral:true,level:'débutant',tags:['conducteur','anti-douleur dos'],info:'Assis. Pose la cheville droite sur le genou gauche. Appuie doucement sur le genou droit vers le bas. Piriforme et fessier profond. Contre la compression du nerf sciatique. 60 sec par côté.'},
{id:'rm_adductor_rock',cat:'mobilite',name:'Adductor rock back',icon:'🦵',duration:45,unit:'sec',reps:10,bilateral:true,level:'débutant',tags:['conducteur','post-sport'],info:'À 4 pattes. Un genou écarté à 90° sur le côté. Recule les hanches vers l\'arrière en gardant ce genou au sol. 10 reps lentes par côté. Adducteurs profonds et capsule articulaire. Complément indispensable du frog stretch.'},
{id:'rm_rot_bassin',cat:'mobilite',name:'Rotations de bassin debout',icon:'🦵',duration:60,unit:'sec',reps:15,bilateral:false,level:'débutant',tags:['réveil','conducteur'],info:'Debout, mains sur les hanches. Grands cercles lents du bassin. 15 dans chaque sens. Mobilise les jonctions L4-L5 et L5-S1. Idéal comme échauffement ou au réveil. Soulage les raideurs matinales en quelques secondes.'},
{id:'rm_thomas',cat:'mobilite',name:'Thomas stretch modifié',icon:'🦵',duration:45,unit:'sec',bilateral:true,level:'intermédiaire',tags:['conducteur','anti-douleur dos'],info:'Allongé en bord de table ou lit. Un genou contre la poitrine, l\'autre jambe pend librement. Droit antérieur et iliopsoas profond. 45 sec par côté. Test et correction de la rétraction du hip flexor, problème no. 1 des personnes assis toute la journée.'},
{id:'rm_hip_90_rot',cat:'mobilite',name:'Rotation interne hanche au sol',icon:'🦵',duration:45,unit:'sec',reps:10,bilateral:true,level:'débutant',tags:['conducteur','anti-douleur dos'],info:'Assis au sol, jambes pliées devant. Laisse tomber les deux genoux du même côté (rotation interne d\'un côté, externe de l\'autre). Reviens au centre et bascule de l\'autre côté. 10 reps lentes. Travaille la rotation interne souvent négligée.'}
];

const RECUP_CAT={
  yoga:{color:'#bf9a4a',bg:'#2a2a1a',border:'#bf9a4a',label:'Yoga',dot:'#bf9a4a'},
  stretch:{color:'#4a8abf',bg:'#1a2535',border:'#4a8abf',label:'Stretching',dot:'#4a8abf'},
  mobilite:{color:'#6ab06a',bg:'#1a3a1a',border:'#6ab06a',label:'Mobilité',dot:'#6ab06a'}
};

const RECUP_LEVEL={
  'débutant':{color:'#4caf7d',bg:'#0d2a0d'},
  'intermédiaire':{color:'#e8c94a',bg:'#2a2a0d'},
  'avancé':{color:'#e85a4a',bg:'#2a0d0d'}
};

const RECUP_PROGRAMS=[
  {id:'prog_matin',name:'Routine réveil',icon:'🌅',color:'#bf9a4a',duration:'10 min',description:'Activer le corps en douceur, libérer les raideurs nocturnes.',exercises:['ry_cat_cow','rm_rot_bassin','ry_cobra','rs_lombaires','ry_enfant','ry_torsion']},
  {id:'prog_postmuscu',name:'Récup post-séance',icon:'💪',color:'#4a8abf',duration:'15 min',description:'Réduire les DOMS, maintenir l\'amplitude articulaire.',exercises:['rs_quad','rs_ischio','rs_pec','rs_grand_dorsal','rs_trapeze','rs_fessier4']},
  {id:'prog_hanches',name:'Mobilité hanches complète',icon:'🦵',color:'#6ab06a',duration:'20 min',description:'Programme complet pour ouvrir et libérer les hanches.',exercises:['rm_rot_bassin','rm_9090','rm_frog','rm_world','rm_cossack','rm_adductor_rock','rm_piriforme']},
  {id:'prog_soir',name:'Détente soir',icon:'😴',color:'#8a6abf',duration:'15 min',description:'Calmer le système nerveux, préparer le sommeil.',exercises:['ry_torsion','ry_happy_baby','ry_pigeon','ry_jambes_mur','ry_papillon','ry_savasana']},
  {id:'prog_mobilite',name:'Mobilité sportive',icon:'🏃',color:'#4caf7d',duration:'15 min',description:'Mobilité dynamique avant ou après l\'effort.',exercises:['rm_hip_circle','rm_world','rm_lateral_lunge','rm_hip_rot','rm_deep_squat','rm_cars']},
  {id:'prog_dos',name:'Récup dos & épaules',icon:'🔙',color:'#5a9abf',duration:'15 min',description:'Soulager les tensions dorsales et cervicales.',exercises:['rs_lombaires','rs_grand_dorsal','rs_trapeze','rs_epaule','ry_cobra','ry_torsion','ry_enfant']},
  {id:'prog_conducteur',name:'Programme conducteur',icon:'🚗',color:'#e8943a',duration:'20 min',description:'Contrer les effets de la position assise prolongée.',exercises:['rm_rot_bassin','ry_fente_basse','rs_hip_flex','rm_9090','rs_psoas_sol','rm_thomas','rs_pec','ry_malasana']}
];

const RECUP_MUSCLE_SUGGEST={
  dos:   {progs:['prog_dos'],exs:['rs_grand_dorsal','ry_enfant','ry_torsion']},
  dos_epaules:{progs:['prog_dos'],exs:['rs_grand_dorsal','rs_trapeze','rs_epaule']},
  pecs_triceps:{progs:['prog_postmuscu'],exs:['rs_pec','rs_pec_sol','rs_thoracique']},
  jambes_fessiers:{progs:['prog_hanches','prog_conducteur'],exs:['rs_quad','rs_ischio','rs_fessier4']},
  biceps_isole:{progs:['prog_postmuscu'],exs:['rs_epaule','rs_triceps','ry_chien']}
};

function getRecupRecommendations(){
  const tiredParts=new Set();
  MUSCLE_GROUPS.forEach(g=>{
    const rec=getRecoveryStatus(g.id);
    if(rec.status==='red'||rec.status==='orange'){
      (GROUP_BODYPARTS[g.id]||[]).forEach(p=>tiredParts.add(p));
    }
  });
  return RECUP_ACTIVITIES.map(act=>{
    const conflicts=act.solicits.filter(s=>tiredParts.has(s));
    let label,color,bg;
    if(conflicts.length===0){label='✅ Recommandé';color='#4caf7d';bg='#1a3a1a';}
    else if(conflicts.length===1){label='⚡ Neutre';color='#e8c94a';bg='#2a2a1a';}
    else{label='⛔ Déconseillé';color='#e85a4a';bg='#2a1a1a';}
    return{...act,conflicts,label,color,bg};
  }).sort((a,b)=>a.conflicts.length-b.conflicts.length);
}

// ══ FOOD DATA ══
const BASE_FOODS_RAW=[
  {name:"Abricot pays (1 ~40g)",p:0.5,l:0,g:8,f:0.8},
  {name:"Betterave lactofermentée (100g)",p:1.5,l:0,g:9,f:2.0},
  {name:"Blanc de poulet cuit (100g)",p:31,l:3.5,g:0,f:0},
  {name:"Calamar grillé/vapeur (100g)",p:18,l:1.5,g:1,f:0},
  {name:"Cerneaux de noix (1 ~5g)",p:0.5,l:3,g:0.5,f:0.2},
  {name:"Cuisse poulet sans peau (100g)",p:23,l:5,g:0,f:0},
  {name:"Cuisse poulet avec peau (100g)",p:23,l:12,g:0,f:0},
  {name:"Datte Mazafati (1 unité ~8g)",p:0.2,l:0,g:6,f:0.5},
  {name:"Flocons d'avoine (100g)",p:13,l:7,g:60,f:10},
  {name:"Foie de veau (100g)",p:20,l:5,g:2,f:0},
  {name:"Graines chanvre décort. (15g)",p:5,l:7,g:2,f:1.2},
  {name:"Graines de chia (15g)",p:2.5,l:4,g:5,f:5},
  {name:"Huile d'olive (1 cac 5ml)",p:0,l:5,g:0,f:0},
  {name:"Huile d'olive (1 cas 15ml)",p:0,l:14,g:0,f:0},
  {name:"Kiwi (1)",p:1,l:0,g:10,f:2},
  {name:"Maquereau boite (125g égoutté)",p:24,l:16,g:0,f:0},
  {name:"Maquereau grillé (100g)",p:20,l:13,g:0,f:0},
  {name:"Mâche (50g)",p:1,l:0,g:1,f:1},
  {name:"Moules cuites (100g)",p:12,l:2,g:3.5,f:0},
  {name:"Noisettes (5)",p:1,l:3,g:1,f:0.8},
  {name:"Noix du Brésil (1)",p:1,l:2,g:0.5,f:0.2},
  {name:"Oeuf entier (1)",p:6,l:5,g:0,f:0},
  {name:"Pain de seigle (40g)",p:4,l:1,g:22,f:3.5},
  {name:"Pâtes cuites (100g)",p:5,l:1,g:25,f:1.8},
  {name:"Patate douce cuite (100g)",p:1.5,l:0.1,g:20,f:3},
  {name:"Quinoa cuit (100g)",p:4,l:2,g:21,f:2.8},
  {name:"Reuteri maison (100ml)",p:3.5,l:3,g:5,f:0},
  {name:"Riz basmati cuit (100g)",p:2,l:0,g:28,f:0.5},
  {name:"Riz nerone cuit (100g)",p:4,l:0.5,g:26,f:2},
  {name:"Sardines au naturel (1 unité ~30g)",p:6,l:2,g:0,f:0},
  {name:"Sardines huile olive (1 unité ~30g)",p:6,l:4,g:0,f:0},
  {name:"Skyr maison 6h égouttage (100g)",p:11,l:1,g:4,f:0},
  {name:"Sarrasin cuit (100g)",p:3.5,l:0.6,g:20,f:2.7},
  {name:"Banane mûre (1 ~120g)",p:1,l:0,g:27,f:3},
  {name:"Papaye verte crue râpée (100g)",p:0.5,l:0,g:7,f:2.5},
  {name:"Pamplemousse (1 ~200g)",p:1.5,l:0.2,g:18,f:2.5},
  {name:"ATTENTION Foie morue (100g) 50g lipides",p:15,l:50,g:0,f:0},
];
const DEFAULT_FAVS=[
  {name:"Petit-déj standard",items:[{name:"Flocons d'avoine (100g)",p:13,l:7,g:60,baseP:13,baseL:7,baseG:60,qty:1,f:10},{name:"Skyr maison 6h égouttage (100g)",p:22,l:2,g:8,baseP:11,baseL:1,baseG:4,qty:2,f:0}]},
  {name:"Dîner poulet/riz",items:[{name:"Cuisse poulet sans peau (100g)",p:55.2,l:12,g:0,baseP:23,baseL:5,baseG:0,qty:2.4,f:0},{name:"Riz basmati cuit (100g)",p:5,l:0,g:70,baseP:2,baseL:0,baseG:28,qty:2.5,f:0.5}]},
];
const MEALS=["Petit-déjeuner","Déjeuner","Collation","Dîner"];
const DEFAULT_PROT=165,DEFAULT_GLUC=300,DEFAULT_FIBER=32;
const LIP_WARN=10,LIP_MAX=15;
const START_DATE='2026-04-30',START_WEIGHT=69.5;
const MILESTONES=[{label:'Fin mai 2026',target:73.5},{label:'Fin juin 2026',target:75.5},{label:'Fin octobre 2026',target:82.5}];

// ══ STATE ══
let currentMeal=0,qty=1,mode='list',currentDate=todayKey(),currentView='repas';
let poidsDate=todayKey();
let lastAdded=null,qtyEditTarget=null,foodSearchTerm='',pendingFavItems=null;
let searchDebounce=null,favOpen=false,selectedFoodIdx=null,editingFood=null;
let muscuSubView='home',muscuGroupId=null,muscuPendingGroupId=null,muscuWeekOffset=0;
let exModalState={gid:null,exId:null,isNew:false},recModalGid=null;
let weightExTarget={gid:null,exId:null,isPerso:false,persoIdx:-1};
let libModalGid=null,libTab='lib',libFilter='all',libSearch='',libSearchDebounce=null,libAddedCount=0;
let persoExercises=[],persoName='Ma séance perso',persoRunning=false;
let aleaType=null,aleaDuration=30,aleaGroupId=null,aleaSession=null;
let pastSessionDaysAgo=0,pastSessionMood='💪';
let showAllSessions=false;
// RECUP V2 STATE
let recupSubView='home',recupProgId=null,recupPersoExs=[],recupPersoName='Ma séance récup',recupAleaCat=null,recupAleaDuration=15,recupAleaResult=null,recupLibFilter='all',recupLibSearch='',recupFavs=null;
let recupSessionActive=false,recupSessionExs=[],recupSessionName='',recupSessionChecked=new Set(),recupTimers={};
// ✅ SESSION DRAFT — validation exercice par exercice
let sessionChecked=new Set();

// ══ HELPERS ══
function fmtEquipment(ex){if(!ex.equipment)return'';const kg=ex.weight!=null?ex.weight:12;if(ex.equipment.includes('Kettlebell'))return ex.equipment.replace('Kettlebell','Kettlebell · '+kg+'kg');return ex.equipment;}
function getWeeklyVolume(){const data=loadGymData();const today=new Date();const dow=today.getDay();const monday=new Date(today);monday.setDate(today.getDate()-(dow===0?6:dow-1));monday.setHours(0,0,0,0);const weekSessions=(data.sessions||[]).filter(s=>new Date(s.date)>=monday);const groupCounts={};weekSessions.forEach(s=>{const g=MUSCLE_GROUPS.find(x=>x.id===s.gid);const name=g?g.name.split('+')[0].trim():(s.gid==='_perso'?'Perso':s.gid==='_alea'?'Aléatoire':null);if(name)groupCounts[name]=(groupCounts[name]||0)+1;});return{total:weekSessions.length,groups:groupCounts};}

// ══ STORAGE ══
function todayKey(){return dateToKey(new Date());}
function dateToKey(d){return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0');}
// ✅ FIX TIMEZONE : utilise la date locale du device (pas UTC)
function isoToLocalKey(isoStr){const d=new Date(isoStr);return dateToKey(d);}
function store(k,v){try{localStorage.setItem(k,JSON.stringify(v));}catch(e){}}
function retrieve(k,def){try{const v=localStorage.getItem(k);if(v!==null)return JSON.parse(v);}catch(e){}return def;}
function loadDay(k){return retrieve('vt_day_'+k,{'Petit-déjeuner':[],'Déjeuner':[],'Collation':[],'Dîner':[]});}
function saveDay(k,d){store('vt_day_'+k,d);}
function getMealData(){return loadDay(currentDate);}
function loadCustomFoods(){return retrieve('vt_cf',[]);}
function saveCustomFoods(f){store('vt_cf',f);}
function loadFoodUsage(){return retrieve('vt_fu',{});}
function incrementUsage(n){const u=loadFoodUsage();u[n]=(u[n]||0)+1;store('vt_fu',u);}
function loadFavorites(){const s=retrieve('vt_favs',null);if(s)return s;store('vt_favs',DEFAULT_FAVS);return DEFAULT_FAVS;}
function saveFavorites(f){store('vt_favs',f);}
function loadWeights(){return retrieve('vt_wts',{});}
function saveWeightFn(date,val){const w=loadWeights();w[date]=val;store('vt_wts',w);}
function loadObjective(){return retrieve('vt_obj',{target:82.5});}
function saveObjectiveFn(obj){store('vt_obj',obj);}
function loadTargets(){return retrieve('vt_targets',{prot:DEFAULT_PROT,gluc:DEFAULT_GLUC,fiber:DEFAULT_FIBER});}
function saveTargets(t){store('vt_targets',t);}
function PROT_TARGET(){return loadTargets().prot;}
function GLUC_TARGET(){return loadTargets().gluc;}
function FIBER_TARGET(){return loadTargets().fiber||DEFAULT_FIBER;}
function loadGymData(){return retrieve('vt_gym',{sessions:[],records:{}});}
function saveGymData(d){store('vt_gym',d);}
function loadGymPrograms(){return retrieve('vt_gym_progs',{});}
function saveGymPrograms(p){store('vt_gym_progs',p);}
function loadGymRecovery(){return retrieve('vt_gym_rec',{...DEFAULT_RECOVERY});}
function saveGymRecovery(r){store('vt_gym_rec',r);}
function loadPersoList(){return retrieve('vt_gym_perso',[]);}
function savePersoList(l){store('vt_gym_perso',l);}
// ✅ Session draft storage
function loadSessionDraft(){return retrieve('vt_session_draft',null);}
function saveSessionDraft(d){store('vt_session_draft',d);}
function clearSessionDraft(){try{localStorage.removeItem('vt_session_draft');}catch(e){}}
// Recup log
function loadRecupLog(){return retrieve('vt_recup_log',[]);}
function saveRecupLog(l){store('vt_recup_log',l);}
function loadRecupSessions(){return retrieve('vt_recup_sessions',[]);}
function saveRecupSessions(l){store('vt_recup_sessions',l);}
function loadRecupPersoList(){return retrieve('vt_recup_perso',[]);}
function saveRecupPersoList(l){store('vt_recup_perso',l);}
function loadRecupFavs(){if(recupFavs)return recupFavs;recupFavs=retrieve('vt_recup_favs',[]);return recupFavs;}
function saveRecupFavs(f){recupFavs=f;store('vt_recup_favs',f);}
function toggleRecupFav(id){const f=loadRecupFavs();const idx=f.indexOf(id);if(idx>=0)f.splice(idx,1);else f.push(id);saveRecupFavs(f);}
function isRecupFav(id){return loadRecupFavs().includes(id);}

function getGroupProgram(gid){const custom=loadGymPrograms();if(custom[gid])return JSON.parse(JSON.stringify(custom[gid]));const g=MUSCLE_GROUPS.find(x=>x.id===gid);return g?JSON.parse(JSON.stringify(g.exercises)):[];}
function saveGroupProgram(gid,exs){const p=loadGymPrograms();p[gid]=exs;saveGymPrograms(p);}
function getRecovery(gid){const r=loadGymRecovery();return r[gid]||DEFAULT_RECOVERY[gid]||72;}

function getRecoveryStatus(gid){
  const data=loadGymData();const linked=LINKED_GROUPS[gid]||[];const allGids=[gid,...linked];
  const sessions=(data.sessions||[]).filter(s=>allGids.includes(s.gid));
  let last=null,hoursAgo=Infinity,linkedUsed=false,linkedName='';
  if(sessions.length){
    last=sessions.reduce((a,b)=>new Date(a.date)>new Date(b.date)?a:b);
    hoursAgo=(Date.now()-new Date(last.date))/(1000*3600);
    linkedUsed=last.gid!==gid;
    linkedName=linkedUsed?(MUSCLE_GROUPS.find(x=>x.id===last.gid)||{name:last.gid}).name:'';
  }
  const rec=getRecovery(gid);
  let effectiveRec=rec;
  let daysAgo=hoursAgo===Infinity?null:Math.floor(hoursAgo/24);
  let status,label;
  if(hoursAgo===Infinity){status='green';label='Jamais fait';}
  else if(hoursAgo>=rec){status='green';label='Prêt ✓';}
  else if(hoursAgo>=rec*0.6){status='orange';label='Limite';}
  else{status='red';label='Repos encore '+Math.ceil(rec-hoursAgo)+'h';}
  // Liens partiels croisés (ex: dos_epaules <-> pecs_triceps, plafond 48h)
  const partial=LINKED_GROUPS_PARTIAL[gid];
  if(partial&&status==='green'){
    const pSess=(data.sessions||[]).filter(s=>partial.groups.includes(s.gid));
    if(pSess.length){
      const pLast=pSess.reduce((a,b)=>new Date(a.date)>new Date(b.date)?a:b);
      const pH=(Date.now()-new Date(pLast.date))/(1000*3600);
      if(pH<partial.maxRecovery){
        hoursAgo=pH;effectiveRec=partial.maxRecovery;daysAgo=Math.floor(pH/24);
        linkedUsed=true;linkedName=(MUSCLE_GROUPS.find(x=>x.id===pLast.gid)||{name:pLast.gid}).name;
        const pPct=pH/partial.maxRecovery;
        status=pPct>=0.6?'orange':'red';
        label=status==='orange'?'Limite':'Repos encore '+Math.ceil(partial.maxRecovery-pH)+'h';
      }
    }
  }
  const remainingH=(status==='red'||status==='orange')?Math.ceil(effectiveRec-(hoursAgo===Infinity?0:hoursAgo)):0;
  const sublabel=status==='orange'?'encore '+remainingH+'h':'';
  return{status,label,sublabel,hoursAgo:hoursAgo===Infinity?null:hoursAgo,daysAgo,linkedUsed,linkedName,remainingH,effectiveRec};
}
function getLastSession(gid){const data=loadGymData();const sessions=(data.sessions||[]).filter(s=>s.gid===gid);return sessions.length?sessions[sessions.length-1]:null;}
function getTotalSessions(){return (loadGymData().sessions||[]).length;}
function getTractionsRecord(){const d=loadGymData();return d.records&&d.records.tractions?d.records.tractions:null;}
function getTractionsWeekCount(){return getWeekGymSessions().reduce(function(t,d){return t+d.sessions.length;},0);}
function hasUpgrade(gid){const custom=loadGymPrograms();if(!custom[gid])return false;const g=MUSCLE_GROUPS.find(x=>x.id===gid);if(!g)return false;return custom[gid].some(ce=>{const de=g.exercises.find(x=>x.id===ce.id);return de&&(ce.sets>de.sets||ce.reps>de.reps);});}
function getSuggestedGroups(){const available=MUSCLE_GROUPS.filter(g=>getRecoveryStatus(g.id).status==='green');if(!available.length)return[];const priority=['dos','dos_epaules','pecs_triceps','jambes_fessiers','biceps_isole'];const sorted=[];priority.forEach(p=>{const g=available.find(x=>x.id===p);if(g)sorted.push(g);});available.forEach(g=>{if(!sorted.find(x=>x.id===g.id))sorted.push(g);});return sorted.slice(0,2);}

// ✅ FIX TIMEZONE : filtre par date locale, plus par startsWith sur UTC
function getWeekGymSessions(){return getWeekGymSessionsAt(0);}
function getWeekGymSessionsAt(offset){
  const data=loadGymData();const today=new Date();const dow=today.getDay();
  const monday=new Date(today);monday.setDate(today.getDate()-(dow===0?6:dow-1)+(offset*7));monday.setHours(0,0,0,0);
  const days=[];
  for(let i=0;i<7;i++){
    const d=new Date(monday);d.setDate(monday.getDate()+i);const key=dateToKey(d);
    const daySessions=(data.sessions||[]).filter(s=>isoToLocalKey(s.date)===key);
    days.push({date:d,key,sessions:daySessions,isToday:key===todayKey()});
  }
  return days;
}
function formatWeekLabel(days){const f=days[0].date,l=days[6].date;return f.getDate()+'/'+(f.getMonth()+1)+' – '+l.getDate()+'/'+(l.getMonth()+1);}
function getLastGymSessions(n){const data=loadGymData();const sessions=[...(data.sessions||[])];sessions.sort((a,b)=>new Date(b.date)-new Date(a.date));return sessions.slice(0,n);}
function getRecentExerciseIds(hoursBack){const data=loadGymData();const cutoff=Date.now()-hoursBack*3600000;const recent=new Set();(data.sessions||[]).filter(s=>new Date(s.date)>cutoff).forEach(s=>{const g=MUSCLE_GROUPS.find(x=>x.id===s.gid);if(g)g.exercises.forEach(e=>recent.add(e.id));const custom=loadGymPrograms();if(custom[s.gid])custom[s.gid].forEach(e=>recent.add(e.id));});return recent;}

// ══ GYM ACTIONS ══
function openGroup(gid){muscuSubView='group';muscuGroupId=gid;renderMain();window.scrollTo(0,0);}
function backToMuscu(){muscuSubView='home';muscuGroupId=null;renderMain();window.scrollTo(0,0);}

// ✅ startSession — reprend le draft automatiquement
function startSession(gid){
  const draft=loadSessionDraft();
  if(draft&&draft.gid===gid){sessionChecked=new Set(draft.checked||[]);}
  else{sessionChecked=new Set();saveSessionDraft({gid,date:todayKey(),checked:[]});}
  muscuSubView='session';muscuGroupId=gid;muscuPendingGroupId=gid;
  document.body.classList.add('session-active');renderMain();window.scrollTo(0,0);
}

// ✅ Toggle check exercice + auto-save draft
function toggleExCheck(exId){
  if(sessionChecked.has(exId))sessionChecked.delete(exId);else sessionChecked.add(exId);
  const draft=loadSessionDraft()||{gid:muscuGroupId,date:todayKey()};
  draft.checked=[...sessionChecked];saveSessionDraft(draft);
  renderMain();
}

function exitSession(){showModal('Quitter la séance sans enregistrer ?',()=>{clearSessionDraft();sessionChecked=new Set();muscuSubView='group';document.body.classList.remove('session-active');renderMain();window.scrollTo(0,0);});}
function endSession(){document.getElementById('mood-modal').style.display='flex';}

function generateStretchesForGroups(groups){
  const DB={'dos':[{name:'Étirement grand dorsal',info:'Bras tendu accroché à la barre. Genoux fléchis. 3 × 30 sec de chaque côté.'}],'épaules':[{name:'Étirement épaule postérieure',info:'Bras croisé devant la poitrine. L\'autre bras tire le coude. 2 × 30 sec de chaque côté.'}],'biceps':[{name:'Étirement biceps',info:'Bras tendu en arrière, paume vers le haut, pouce vers le bas. 3 × 30 sec de chaque côté.'}],'triceps':[{name:'Étirement triceps',info:'Bras plié derrière la tête. L\'autre main pousse le coude. 2 × 30 sec de chaque côté.'}],'pectoraux':[{name:'Étirement pectoraux — cadre de porte',info:'Bras en L dans le cadre. 3 hauteurs. 45 sec chaque position.'}],'core':[{name:'Cat-cow',info:'À 4 pattes. Inspiration = dos en creux, expiration = dos en rond. 2 × 12 lentes.'}],'jambes':[{name:'Étirement quadriceps',info:'Talon vers les fesses. 2 × 30 sec de chaque côté.'},{name:'Étirement ischio-jambiers',info:'Jambe tendue sur la chaise. Penche le buste. 2 × 30 sec.'}],'fessiers':[{name:'Étirement fessiers — pigeon',info:'Position du pigeon. 3 × 45 sec de chaque côté.'},{name:'Étirement fléchisseurs de hanche',info:'Fente basse, genou arrière au sol. 2 × 30 sec de chaque côté.'}],'mollets':[{name:'Étirement mollets',info:'Talon au sol, jambe tendue derrière. 2 × 30 sec de chaque côté.'}]};
  const result=[];const seen=new Set();
  groups.forEach(g=>{const gl=(g||'').toLowerCase();const key=Object.keys(DB).find(k=>gl.includes(k));if(key){DB[key].forEach(s=>{if(!seen.has(s.name)){seen.add(s.name);result.push(s);}});}});
  return result;
}

function selectMood(mood){
  const note=(document.getElementById('session-note')?.value||'').trim();
  document.getElementById('session-note').value='';
  document.getElementById('mood-modal').style.display='none';
  const data=loadGymData();
  const session={gid:muscuPendingGroupId,date:new Date().toISOString(),mood};
  if(note)session.note=note;
  data.sessions.push(session);saveGymData(data);
  const isPerso=muscuPendingGroupId==='_perso'||muscuPendingGroupId==='_alea';
  let stretches=[];
  if(isPerso){const groups=new Set();persoExercises.forEach(ex=>{if(ex.groupTarget)groups.add(ex.groupTarget);});stretches=generateStretchesForGroups(groups);}
  else{const g=MUSCLE_GROUPS.find(x=>x.id===muscuPendingGroupId);if(g&&g.stretches)stretches=g.stretches;}
  if(stretches.length){let html='';stretches.forEach(s=>{html+='<div class="stretch-item"><div class="stretch-name">'+s.name+'</div><div class="stretch-info">'+s.info+'</div></div>';});document.getElementById('stretch-content').innerHTML=html;document.getElementById('stretch-modal').style.display='flex';}
  else finishSession();
}

function finishSession(){
  clearSessionDraft();sessionChecked=new Set();
  document.getElementById('stretch-modal').style.display='none';
  document.getElementById('mood-modal').style.display='none';
  document.body.classList.remove('session-active');
  muscuSubView='home';muscuGroupId=null;muscuPendingGroupId=null;persoRunning=false;
  renderAll();showToast('✓ Séance enregistrée !');
}

function adjustEx(gid,exId,field,delta){const exs=getGroupProgram(gid);const ex=exs.find(e=>e.id===exId);if(!ex)return;if(field==='sets')ex.sets=Math.max(1,ex.sets+delta);if(field==='reps')ex.reps=Math.max(1,ex.reps+delta);saveGroupProgram(gid,exs);renderMain();}
function moveEx(gid,exId,dir){const exs=getGroupProgram(gid);const idx=exs.findIndex(e=>e.id===exId);if(idx<0)return;const newIdx=idx+dir;if(newIdx<0||newIdx>=exs.length)return;const tmp=exs[idx];exs[idx]=exs[newIdx];exs[newIdx]=tmp;saveGroupProgram(gid,exs);renderMain();}
function resetGroupProgram(gid){showModal('Revenir au programme par défaut ?',()=>{const p=loadGymPrograms();delete p[gid];saveGymPrograms(p);renderMain();showToast('Programme réinitialisé ✓');});}

function openExEditModal(gid,exId){const exs=getGroupProgram(gid);const ex=exs.find(e=>e.id===exId);if(!ex)return;exModalState={gid,exId,isNew:false};document.getElementById('ex-modal-title').textContent='Modifier l\'exercice';document.getElementById('ex-name').value=ex.name||'';document.getElementById('ex-group-target').value=ex.groupTarget||'';document.getElementById('ex-equipment').value=ex.equipment||'';document.getElementById('ex-sets').value=ex.sets||3;document.getElementById('ex-reps').value=ex.reps||10;document.getElementById('ex-unit').value=ex.unit||'reps';document.getElementById('ex-weight').value=ex.weight||'';document.getElementById('ex-info').value=ex.info||'';document.getElementById('ex-delete-btn').style.display='block';document.getElementById('ex-modal').style.display='flex';}
function openExAddModal(gid){exModalState={gid,exId:null,isNew:true};document.getElementById('ex-modal-title').textContent='Créer un exercice';document.getElementById('ex-name').value='';document.getElementById('ex-group-target').value='';document.getElementById('ex-equipment').value='';document.getElementById('ex-sets').value=3;document.getElementById('ex-reps').value=10;document.getElementById('ex-unit').value='reps';document.getElementById('ex-weight').value='';document.getElementById('ex-info').value='';document.getElementById('ex-delete-btn').style.display='none';document.getElementById('ex-modal').style.display='flex';}
function saveExModal(){const name=document.getElementById('ex-name').value.trim();if(!name){alert('Donne un nom à l\'exercice');return;}const sets=parseInt(document.getElementById('ex-sets').value)||3;const reps=parseInt(document.getElementById('ex-reps').value)||10;const unit=document.getElementById('ex-unit').value;const equipment=document.getElementById('ex-equipment').value.trim();const info=document.getElementById('ex-info').value.trim();const groupTarget=document.getElementById('ex-group-target').value.trim();const weightVal=parseFloat(document.getElementById('ex-weight').value);const weight=isNaN(weightVal)?null:weightVal;const exs=getGroupProgram(exModalState.gid);if(exModalState.isNew){exs.push({id:'custom_'+Date.now(),name,sets,reps,unit,equipment,info,groupTarget,weight});}else{const ex=exs.find(e=>e.id===exModalState.exId);if(ex)Object.assign(ex,{name,sets,reps,unit,equipment,info,groupTarget,weight});}saveGroupProgram(exModalState.gid,exs);document.getElementById('ex-modal').style.display='none';renderMain();showToast('✓ Exercice enregistré');}
function deleteExModal(){showModal('Supprimer cet exercice ?',()=>{const exs=getGroupProgram(exModalState.gid);const idx=exs.findIndex(e=>e.id===exModalState.exId);if(idx>=0)exs.splice(idx,1);saveGroupProgram(exModalState.gid,exs);document.getElementById('ex-modal').style.display='none';renderMain();showToast('Exercice supprimé');});}

// ✅ FIX BOUTON "+" : une seule fonction, gestion perso intégrée (supprime l'override récursif)
function closeLibModal(){document.getElementById('lib-modal').style.display='none';if(libAddedCount>0)showToast('✓ '+libAddedCount+' exercice'+(libAddedCount>1?'s':'')+' ajouté'+(libAddedCount>1?'s':''));libAddedCount=0;renderMain();}
function openLibModal(gid){libModalGid=gid;libTab='lib';libFilter='all';libSearch='';libAddedCount=0;document.getElementById('lib-modal').style.display='flex';renderLibModal();}
function switchLibTab(tab){libTab=tab;document.getElementById('lib-tab-lib').classList.toggle('active',tab==='lib');document.getElementById('lib-tab-custom').classList.toggle('active',tab==='custom');renderLibModal();}
function renderLibModal(){
  const el=document.getElementById('lib-tab-content');
  if(libTab==='lib'){
    const filtered=EXERCISE_LIBRARY.filter(e=>{const groupOk=libFilter==='all'||(libFilter==='jambes'?(e.group==='jambes'||e.group==='mollets'):e.group===libFilter);const searchOk=!libSearch||e.name.toLowerCase().includes(libSearch.toLowerCase());return groupOk&&searchOk;});
    const currentProgram=(libModalGid==='_perso'||libModalGid==='_alea')?persoExercises:(libModalGid?getGroupProgram(libModalGid):[]);const currentNames=new Set(currentProgram.map(e=>e.name));
    let h='<div class="lib-filter-row"><button class="lib-filter-btn'+(libFilter==='all'?' active':'')+'" onclick="libFilter=\'all\';renderLibModal()">Tous</button>';
    LIB_GROUPS.forEach(g=>{const label=g==='jambes'?'Jambes+Mollets':GROUP_NAMES_FR[g];h+='<button class="lib-filter-btn'+(libFilter===g?' active':'')+'" onclick="libFilter=\''+g+'\';renderLibModal()">'+label+'</button>';});
    h+='</div>';
    if(libAddedCount>0)h+='<div style="background:#1a3a1a;border:1px solid #2a5a2a;border-radius:8px;padding:7px 12px;margin-bottom:8px;font-size:12px;color:#4caf7d;font-weight:600;text-align:center">✓ '+libAddedCount+' exercice'+(libAddedCount>1?'s':'')+' ajouté'+(libAddedCount>1?'s':'')+'</div>';
    h+='<input type="text" class="lib-search" placeholder="🔍 Rechercher..." value="'+esc(libSearch)+'" oninput="handleLibSearch(this.value)" id="lib-search-input"><div class="lib-list">';
    if(!filtered.length)h+='<div style="padding:14px;text-align:center;font-size:12px;color:#4a5a6a">Aucun exercice trouvé</div>';
    filtered.forEach(e=>{const alreadyIn=currentNames.has(e.name);const badge=alreadyIn?'<span style="font-size:9px;color:#4caf7d;background:#0d2a0d;border-radius:4px;padding:1px 5px;font-weight:700;flex-shrink:0;white-space:nowrap">✓ Programme</span>':'';h+='<div class="lib-item"><span class="lib-item-tag">'+GROUP_NAMES_FR[e.group]+'</span><span class="lib-item-name">'+e.name+'</span>'+badge+'<span class="lib-item-eq">'+(e.equipment||'')+'</span><button class="lib-item-add" onclick="addFromLibrary(\''+e.id+'\')">+</button></div>';});
    h+='</div>';el.innerHTML=h;
    const inp=document.getElementById('lib-search-input');if(inp)inp.focus();
  } else {
    el.innerHTML='<div style="font-size:12px;color:#6a7a8a;margin-bottom:12px">Crée un exercice et ajoute-le au groupe</div><input type="text" id="lib-c-name" placeholder="Nom de l\'exercice" style="margin-bottom:8px"><input type="text" id="lib-c-group" placeholder="Groupe ciblé (Dos, Biceps...)" style="margin-bottom:8px"><input type="text" id="lib-c-eq" placeholder="Équipement" style="margin-bottom:8px"><div class="custom-row" style="margin-bottom:8px"><div style="flex:1"><label class="modal-label" style="margin-top:0">Séries</label><input type="number" id="lib-c-sets" value="3" min="1" max="10" style="text-align:center"></div><div style="flex:1"><label class="modal-label" style="margin-top:0">Reps/sec</label><input type="number" id="lib-c-reps" value="10" min="1" max="120" style="text-align:center"></div></div><textarea id="lib-c-info" rows="2" placeholder="Description..." style="margin-bottom:12px"></textarea><button class="modal-btn" style="background:#2a5a2a;color:#6ab06a" onclick="addCustomFromLib()">+ Ajouter au groupe</button>';
  }
}
function handleLibSearch(val){libSearch=val;clearTimeout(libSearchDebounce);libSearchDebounce=setTimeout(()=>{const pos=document.getElementById('lib-search-input')?.selectionStart;renderLibModal();const el=document.getElementById('lib-search-input');if(el){el.focus();if(pos!=null)try{el.setSelectionRange(pos,pos);}catch(e){}}},300);}

// ✅ addFromLibrary — fonction unique, gère perso ET groupe normal
function addFromLibrary(libId){
  if(libModalGid==='_perso'||libModalGid==='_alea'){
    const libEx=EXERCISE_LIBRARY.find(e=>e.id===libId);if(!libEx)return;
    persoExercises.push({id:'perso_'+libId+'_'+Date.now(),name:libEx.name,sets:libEx.defaultSets,reps:libEx.defaultReps,unit:libEx.unit,equipment:libEx.equipment,info:libEx.info,groupTarget:GROUP_NAMES_FR[libEx.group]||''});
    libAddedCount++;renderLibModal();return;
  }
  const libEx=EXERCISE_LIBRARY.find(e=>e.id===libId);if(!libEx)return;
  const exs=getGroupProgram(libModalGid);
  exs.push({id:'lib_'+libId+'_'+Date.now(),name:libEx.name,sets:libEx.defaultSets,reps:libEx.defaultReps,unit:libEx.unit,equipment:libEx.equipment,info:libEx.info,groupTarget:GROUP_NAMES_FR[libEx.group]||''});
  saveGroupProgram(libModalGid,exs);libAddedCount++;renderLibModal();
}

// ✅ addCustomFromLib — fonction unique
function addCustomFromLib(){
  const name=document.getElementById('lib-c-name')?.value.trim();if(!name){alert('Donne un nom');return;}
  const groupTarget=document.getElementById('lib-c-group')?.value.trim();
  const equipment=document.getElementById('lib-c-eq')?.value.trim();
  const sets=parseInt(document.getElementById('lib-c-sets')?.value)||3;
  const reps=parseInt(document.getElementById('lib-c-reps')?.value)||10;
  const info=document.getElementById('lib-c-info')?.value.trim();
  if(libModalGid==='_perso'||libModalGid==='_alea'){
    persoExercises.push({id:'custom_'+Date.now(),name,sets,reps,unit:'reps',equipment,info,groupTarget});
    showToast('✓ '+name+' ajouté');document.getElementById('lib-modal').style.display='none';renderMain();return;
  }
  const exs=getGroupProgram(libModalGid);
  exs.push({id:'custom_'+Date.now(),name,sets,reps,unit:'reps',equipment,info,groupTarget});
  saveGroupProgram(libModalGid,exs);showToast('✓ '+name+' ajouté');document.getElementById('lib-modal').style.display='none';renderMain();
}

function openRecModal(gid){recModalGid=gid;document.getElementById('rec-input').value=getRecovery(gid);document.getElementById('rec-modal').style.display='flex';}
function saveRecovery(){const val=parseInt(document.getElementById('rec-input').value)||72;const r=loadGymRecovery();r[recModalGid]=Math.max(24,Math.min(168,val));saveGymRecovery(r);document.getElementById('rec-modal').style.display='none';renderMain();showToast('Récupération mise à jour ✓');}

function openPastSessionModal(){pastSessionDaysAgo=1;pastSessionMood='💪';document.getElementById('past-session-modal').style.display='flex';document.getElementById('past-date-input').value=dateToKey(new Date());setTimeout(()=>setPastDate(1),10);}
function setPastDate(daysAgo){pastSessionDaysAgo=daysAgo;['auj','hier','avh'].forEach((id,i)=>{const el=document.getElementById('past-date-'+id);if(el)el.classList.toggle('active',i===daysAgo);});const d=new Date();d.setDate(d.getDate()-daysAgo);const inp=document.getElementById('past-date-input');if(inp)inp.value=dateToKey(d);}
function setPastDateCustom(val){if(!val)return;['auj','hier','avh'].forEach(id=>{const el=document.getElementById('past-date-'+id);if(el)el.classList.remove('active');});pastSessionDaysAgo=-1;}
function setPastMood(mood){pastSessionMood=mood;const map={'💪':'bien','😐':'moyen','😓':'dur'};['bien','moyen','dur'].forEach(m=>{const el=document.getElementById('past-mood-'+m);if(el)el.classList.toggle('active',map[mood]===m);});}
function savePastSession(){
  const gid=document.getElementById('past-gid').value;let dateStr;
  if(pastSessionDaysAgo>=0){const d=new Date();d.setDate(d.getDate()-pastSessionDaysAgo);d.setHours(12,0,0,0);dateStr=d.toISOString();}
  else{const val=document.getElementById('past-date-input').value;if(!val){alert('Sélectionne une date');return;}dateStr=new Date(val+'T12:00:00').toISOString();}
  const data=loadGymData();data.sessions.push({gid,date:dateStr,mood:pastSessionMood});data.sessions.sort((a,b)=>new Date(a.date)-new Date(b.date));saveGymData(data);
  document.getElementById('past-session-modal').style.display='none';
  const g=MUSCLE_GROUPS.find(x=>x.id===gid);const label=g?g.name:gid==='_perso'?'Séance perso':'Séance aléatoire';const d=new Date(dateStr);
  showToast('✓ '+label+' — '+d.getDate()+'/'+(d.getMonth()+1)+' enregistrée');renderMain();
}
function openWeightModal(gid,exId){weightExTarget={gid,exId,isPerso:false,persoIdx:-1};const exs=getGroupProgram(gid);const ex=exs.find(e=>e.id===exId);document.getElementById('weight-kb-title').textContent=(ex?ex.name:'Exercice')+' — Poids';document.getElementById('weight-kb-input').value=ex&&ex.weight?ex.weight:'';document.getElementById('weight-kb-modal').style.display='flex';}
function openWeightModalPerso(idx){weightExTarget={gid:null,exId:null,isPerso:true,persoIdx:idx};const ex=persoExercises[idx];document.getElementById('weight-kb-title').textContent=(ex?ex.name:'Exercice')+' — Poids';document.getElementById('weight-kb-input').value=ex&&ex.weight?ex.weight:'';document.getElementById('weight-kb-modal').style.display='flex';}
function saveExWeight(){const val=parseFloat(document.getElementById('weight-kb-input').value);const weight=isNaN(val)?null:val;if(weightExTarget.isPerso){const ex=persoExercises[weightExTarget.persoIdx];if(ex)ex.weight=weight;}else{const exs=getGroupProgram(weightExTarget.gid);const ex=exs.find(e=>e.id===weightExTarget.exId);if(ex){ex.weight=weight;saveGroupProgram(weightExTarget.gid,exs);}}document.getElementById('weight-kb-modal').style.display='none';renderMain();showToast(weight?'Poids : '+weight+'kg ✓':'Poids effacé');}
function openTractionsModal(){document.getElementById('tractions-input').value=getTractionsRecord()||'';const data=loadGymData();document.getElementById('tractions-series-input').value=(data.records&&data.records.tractionsSeries)||'';const hist=(data.records&&data.records.tractionsHistory)||[];const histEl=document.getElementById('tractions-history');if(hist.length){let h='<div class="section-title" style="margin-bottom:6px">Historique</div>';[...hist].reverse().slice(0,6).forEach(entry=>{const d=new Date(entry.date);h+='<div class="traction-history-row"><span class="traction-history-date">'+d.getDate()+'/'+(d.getMonth()+1)+'/'+d.getFullYear()+'</span><span class="traction-history-val">'+entry.reps+' reps</span></div>';});histEl.innerHTML=h;}else histEl.innerHTML='<div style="font-size:11px;color:#3a4a5a;text-align:center;padding:6px 0">Aucun historique pour l\'instant</div>';document.getElementById('tractions-modal').style.display='flex';}
function saveTractions(){const val=parseInt(document.getElementById('tractions-input').value);if(isNaN(val)||val<1)return;const data=loadGymData();if(!data.records)data.records={};const prev=data.records.tractions;data.records.tractions=val;const series=parseInt(document.getElementById('tractions-series-input').value);if(!isNaN(series)&&series>=1)data.records.tractionsSeries=series;if(!data.records.tractionsHistory)data.records.tractionsHistory=[];if(val!==prev){data.records.tractionsHistory.push({date:new Date().toISOString(),reps:val});if(data.records.tractionsHistory.length>20)data.records.tractionsHistory=data.records.tractionsHistory.slice(-20);}saveGymData(data);document.getElementById('tractions-modal').style.display='none';renderMain();showToast(prev&&val>prev?'🏆 Nouveau record : '+val+' reps !':'Record tractions : '+val+' reps ✓');}
function showExInfo(name,info){document.getElementById('info-modal-title').textContent=name;document.getElementById('info-modal-body').textContent=info;document.getElementById('info-modal').style.display='flex';}

function openPerso(){muscuSubView='perso';renderMain();window.scrollTo(0,0);}
function backFromPerso(){muscuSubView='home';renderMain();window.scrollTo(0,0);}
function openPersoLib(){libModalGid='_perso';libTab='lib';libFilter='all';libSearch='';libAddedCount=0;document.getElementById('lib-modal').style.display='flex';renderLibModal();}
function removePersoEx(idx){persoExercises.splice(idx,1);renderMain();}
function movePersoEx(idx,dir){const newIdx=idx+dir;if(newIdx<0||newIdx>=persoExercises.length)return;const tmp=persoExercises[idx];persoExercises[idx]=persoExercises[newIdx];persoExercises[newIdx]=tmp;renderMain();}
function adjustPersoEx(idx,field,delta){const ex=persoExercises[idx];if(!ex)return;if(field==='sets')ex.sets=Math.max(1,ex.sets+delta);if(field==='reps')ex.reps=Math.max(1,ex.reps+delta);renderMain();}
function savePerso(){document.getElementById('perso-save-name').value=persoName;document.getElementById('perso-save-modal').style.display='flex';}
function confirmSavePerso(){const name=document.getElementById('perso-save-name').value.trim()||'Ma séance';const list=loadPersoList();list.push({id:'perso_'+Date.now(),name,exercises:JSON.parse(JSON.stringify(persoExercises))});savePersoList(list);document.getElementById('perso-save-modal').style.display='none';showToast('✓ Séance "'+name+'" sauvegardée');}
function loadPersoSession(id){const list=loadPersoList();const item=list.find(x=>x.id===id);if(!item)return;persoExercises=JSON.parse(JSON.stringify(item.exercises));persoName=item.name;muscuSubView='perso';renderMain();setTimeout(()=>{const inp=document.querySelector('.perso-name-input');if(inp)inp.value=persoName;},30);window.scrollTo(0,0);}
function deletePersoSession(id){showModal('Supprimer cette séance sauvegardée ?',()=>{const list=loadPersoList().filter(x=>x.id!==id);savePersoList(list);renderMain();showToast('Séance supprimée');});}

function startPersoSession(){
  if(!persoExercises.length){alert('Ajoute au moins un exercice');return;}
  const draft=loadSessionDraft();
  if(draft&&draft.gid==='_perso'){sessionChecked=new Set(draft.checked||[]);}
  else{sessionChecked=new Set();saveSessionDraft({gid:'_perso',date:todayKey(),checked:[]});}
  muscuSubView='session';muscuGroupId='_perso';muscuPendingGroupId='_perso';
  document.body.classList.add('session-active');persoRunning=true;renderMain();window.scrollTo(0,0);
}
function startAleaSession(){
  if(!aleaSession||!aleaSession.length)return;
  persoExercises=aleaSession.map(e=>({id:'alea_'+e.id+'_'+Date.now(),name:e.name||e.id,sets:e.defaultSets||e.sets||3,reps:e.defaultReps||e.reps||10,unit:e.unit||'reps',equipment:e.equipment||'',info:e.info||'',groupTarget:GROUP_NAMES_FR[e.group]||''}));
  sessionChecked=new Set();saveSessionDraft({gid:'_alea',date:todayKey(),checked:[]});
  muscuSubView='session';muscuGroupId='_alea';muscuPendingGroupId='_alea';
  document.body.classList.add('session-active');persoRunning=true;renderMain();window.scrollTo(0,0);
}
function openAlea(){muscuSubView='alea';aleaSession=null;renderMain();window.scrollTo(0,0);}
function backFromAlea(){muscuSubView='home';renderMain();window.scrollTo(0,0);}
function generateAlea(){
  const recentIds=getRecentExerciseIds(24);let result=[];
  if(aleaType==='balanced'){const groups=['dos','epaules','pecs','core','jambes','fessiers'];groups.forEach(g=>{const avail=EXERCISE_LIBRARY.filter(e=>e.group===g&&!recentIds.has(e.id));if(avail.length){result.push(avail[Math.floor(Math.random()*avail.length)]);}});const armGroup=Math.random()<0.5?'biceps':'triceps';const armAvail=EXERCISE_LIBRARY.filter(e=>e.group===armGroup&&!recentIds.has(e.id));if(armAvail.length)result.push(armAvail[Math.floor(Math.random()*armAvail.length)]);result=result.sort(()=>Math.random()-0.5);}
  else if(aleaType==='duration'){const count=Math.max(3,Math.round(aleaDuration*0.2));const avail=EXERCISE_LIBRARY.filter(e=>!recentIds.has(e.id)).sort(()=>Math.random()-0.5);result=avail.slice(0,count);}
  else if(aleaType==='group'&&aleaGroupId){const g=MUSCLE_GROUPS.find(x=>x.id===aleaGroupId);if(g){const shuffled=[...g.exercises].filter(e=>!recentIds.has(e.id)).sort(()=>Math.random()-0.5);result=shuffled.slice(0,Math.min(8,shuffled.length));if(!result.length)result=[...g.exercises].sort(()=>Math.random()-0.5).slice(0,6);}}
  aleaSession=result;renderMain();
}

// ══ RECUP ACTIONS ══
function logRecupActivity(actId){
  const act=RECUP_ACTIVITIES.find(a=>a.id===actId);if(!act)return;
  const log=loadRecupLog();
  log.unshift({id:'r_'+Date.now(),date:new Date().toISOString(),type:'activity',activityId:actId,activityName:act.name,name:act.name,duration:act.duration});
  if(log.length>50)log.splice(50);
  saveRecupLog(log);showToast('✓ '+act.name+' enregistré !');renderMain();
}
function deleteRecupEntry(id){showModal('Supprimer cette entrée ?',()=>{const log=loadRecupLog().filter(e=>e.id!==id);saveRecupLog(log);renderMain();});}
function deleteRecupEntryAll(id){
  showModal('Supprimer cette entrée ?',()=>{
    saveRecupLog(loadRecupLog().filter(e=>e.id!==id));
    saveRecupSessions(loadRecupSessions().filter(e=>e.id!==id));
    renderMain();
  });
}
function logRecupSession(progId,name,duration){
  const sessions=loadRecupSessions();
  sessions.unshift({id:'rs_'+Date.now(),date:new Date().toISOString(),type:'session',name:name||'Séance récup',duration:duration||'',progId:progId||null});
  if(sessions.length>100)sessions.splice(100);
  saveRecupSessions(sessions);
  showToast('✓ '+name+' enregistrée !');
  recupSubView='home';recupSessionActive=false;renderMain();
}
function logRecupAleaSession(){
  if(!recupAleaResult||!recupAleaResult.length)return;
  const cats=[...new Set(recupAleaResult.map(e=>e.cat))];
  const icon=cats.length===1?(cats[0]==='yoga'?'🧘':cats[0]==='stretch'?'🤸':'🦵'):'🌀';
  const name=cats.length===1?(RECUP_CAT[cats[0]]||{label:'Séance'}).label+' aléatoire':'Séance mixte aléatoire';
  logRecupSession(null,icon+' '+name,recupAleaDuration+' min');
}
function openRecupProg(id){recupProgId=id;recupSubView='prog';renderMain();window.scrollTo(0,0);}
function openRecupLibForPerso(){recupSubView='library';renderMain();window.scrollTo(0,0);}
function addRecupExToPerso(libId){
  const e=RECUP_LIBRARY.find(x=>x.id===libId);if(!e)return;
  recupPersoExs.push(JSON.parse(JSON.stringify(e)));
  showToast('✓ '+e.name+' ajouté');
  recupSubView='perso';renderMain();
}
function removeRecupPersoEx(idx){recupPersoExs.splice(idx,1);renderMain();}
function moveRecupPersoEx(idx,dir){const ni=idx+dir;if(ni<0||ni>=recupPersoExs.length)return;const tmp=recupPersoExs[idx];recupPersoExs[idx]=recupPersoExs[ni];recupPersoExs[ni]=tmp;renderMain();}
function saveRecupPerso(){
  const name=recupPersoName.trim()||'Ma séance récup';
  const list=loadRecupPersoList();
  list.push({id:'rp_'+Date.now(),name,exercises:JSON.parse(JSON.stringify(recupPersoExs))});
  saveRecupPersoList(list);showToast('✓ "'+name+'" sauvegardée');
}
function loadRecupPersoSession(id){
  const list=loadRecupPersoList();const item=list.find(x=>x.id===id);if(!item)return;
  recupPersoExs=JSON.parse(JSON.stringify(item.exercises));recupPersoName=item.name;renderMain();
}
function deleteRecupPersoSession(id){showModal('Supprimer cette séance ?',()=>{saveRecupPersoList(loadRecupPersoList().filter(x=>x.id!==id));renderMain();showToast('Séance supprimée');});}
function calcRecupDuration(exs){
  if(!exs||!exs.length)return 0;
  const totalSec=exs.reduce((a,e)=>{const dur=e.duration||30;const bilateral=e.bilateral?2:1;const reps=e.reps?1:1;return a+(dur*bilateral)+15;},0);
  return Math.ceil(totalSec/60);
}
function formatTimerSec(s){const m=Math.floor(s/60);const sc=s%60;return(m>0?m+'m ':'')+sc+'s';}
function generateRecupAlea(){
  const secPerEx=90;const count=Math.max(3,Math.round((recupAleaDuration*60)/secPerEx));
  let pool;
  if(recupAleaCat==='mixed')pool=[...RECUP_LIBRARY];
  else pool=RECUP_LIBRARY.filter(e=>e.cat===recupAleaCat);
  recupAleaResult=pool.sort(()=>Math.random()-0.5).slice(0,Math.min(count,pool.length));
  renderMain();
}
function startRecupSession(progId,name){
  let exs;
  if(progId){const prog=RECUP_PROGRAMS.find(p=>p.id===progId);exs=prog?prog.exercises.map(id=>RECUP_LIBRARY.find(e=>e.id===id)).filter(Boolean):[];}
  else exs=JSON.parse(JSON.stringify(recupPersoExs));
  if(!exs.length)return;
  recupSessionExs=exs.map((e,i)=>({...e,id:e.id+'_'+i}));
  recupSessionName=name||'Séance récup';
  recupSessionChecked=new Set();recupTimers={};recupSessionActive=true;
  renderMain();window.scrollTo(0,0);
}
function startRecupAleaSession(){
  if(!recupAleaResult||!recupAleaResult.length)return;
  const cats=[...new Set(recupAleaResult.map(e=>e.cat))];
  const icon=cats.length===1?(cats[0]==='yoga'?'🧘':cats[0]==='stretch'?'🤸':'🦵'):'🌀';
  const name=cats.length===1?(RECUP_CAT[cats[0]]||{label:'Séance'}).label+' aléatoire':'Séance mixte';
  recupSessionExs=recupAleaResult.map((e,i)=>({...e,id:e.id+'_'+i}));
  recupSessionName=icon+' '+name;recupSessionChecked=new Set();recupTimers={};recupSessionActive=true;
  renderMain();window.scrollTo(0,0);
}
function toggleRecupCheck(id){
  if(recupSessionChecked.has(id))recupSessionChecked.delete(id);else recupSessionChecked.add(id);
  renderMain();
}
function toggleRecupTimer(id,totalSec){
  if(!recupTimers[id])recupTimers[id]={left:totalSec,running:false,interval:null};
  const t=recupTimers[id];
  if(t.running){clearInterval(t.interval);t.running=false;}
  else{
    t.running=true;
    t.interval=setInterval(()=>{
      t.left--;
      if(t.left<=0){clearInterval(t.interval);t.running=false;t.left=0;try{navigator.vibrate&&navigator.vibrate([200,100,200]);}catch(e){}showToast('⏱ Terminé !');}
      renderMain();
    },1000);
  }
  renderMain();
}
function exitRecupSession(){
  Object.values(recupTimers).forEach(t=>{if(t.interval)clearInterval(t.interval);});
  recupTimers={};recupSessionActive=false;renderMain();window.scrollTo(0,0);
}
function endRecupSession(){
  Object.values(recupTimers).forEach(t=>{if(t.interval)clearInterval(t.interval);});
  recupTimers={};
  const doneCount=recupSessionExs.filter(e=>recupSessionChecked.has(e.id)).length;
  const pct=recupSessionExs.length>0?Math.round((doneCount/recupSessionExs.length)*100):0;
  const dur='≈'+calcRecupDuration(recupSessionExs)+' min';
  logRecupSession(null,recupSessionName+(pct<100?' ('+pct+'%)':''),dur);
}
function scrollToRecupLog(){renderMain();setTimeout(()=>{const el=document.getElementById('recup-log-anchor');if(el)el.scrollIntoView({behavior:'smooth'});},100);}

// ══ FOOD FUNCTIONS ══
function getAllFoods(){const usage=loadFoodUsage();const deleted=retrieve('vt_del',[]);const base=BASE_FOODS_RAW.filter(f=>!deleted.includes(f.name));const custom=loadCustomFoods();const all=[...base,...custom];all.sort((a,b)=>{const ua=usage[a.name]||0,ub=usage[b.name]||0;if(ub!==ua)return ub-ua;return a.name.localeCompare(b.name);});return all;}
function deleteFoodFn(name){const del=retrieve('vt_del',[]);if(!del.includes(name)){del.push(name);store('vt_del',del);}saveCustomFoods(loadCustomFoods().filter(f=>f.name!==name));}
function mealTotals(items){return items.reduce((a,i)=>({p:a.p+i.p,l:a.l+i.l,g:a.g+(i.g||0),f:a.f+(i.f||0)}),{p:0,l:0,g:0,f:0});}
function dayTotals(data){return MEALS.reduce((a,m)=>{const t=mealTotals(data[m]||[]);return{p:a.p+t.p,l:a.l+t.l,g:a.g+t.g,f:a.f+t.f};},{p:0,l:0,g:0,f:0});}
function r1(n){return Math.round(n*10)/10;}
function esc(s){return String(s).replace(/\\/g,'\\\\').replace(/'/g,"\\'");}
function daysSinceStart(){const start=new Date(START_DATE+'T12:00:00');return Math.floor((new Date()-start)/(1000*60*60*24));}
function calcStreak(){let s=0;const d=new Date();for(let i=0;i<60;i++){const k=dateToKey(d);if(dayTotals(loadDay(k)).p>=PROT_TARGET())s++;else if(i>0)break;d.setDate(d.getDate()-1);}return s;}
function calcAvg7(){let total=0,days=0;const d=new Date();for(let i=0;i<7;i++){const k=dateToKey(d);const tot=dayTotals(loadDay(k));if(tot.p>0){total+=tot.p;days++;}d.setDate(d.getDate()-1);}return days>0?Math.round(total/days):0;}

function switchView(v){
  currentView=v;
  if(v!=='muscu'){muscuSubView='home';muscuGroupId=null;document.body.classList.remove('session-active');}
  ['repas','muscu','recup','poids','data'].forEach(x=>{const el=document.getElementById('nav-'+x);if(el)el.classList.toggle('active',x===v);});
  document.getElementById('main-header').style.display=v==='repas'?'block':'none';
  document.getElementById('tabs').style.display=v==='repas'?'flex':'none';
  renderMain();
}
function prevDay(){const d=new Date(currentDate+'T12:00:00');d.setDate(d.getDate()-1);currentDate=dateToKey(d);renderAll();}
function nextDay(){if(currentDate>=todayKey())return;const d=new Date(currentDate+'T12:00:00');d.setDate(d.getDate()+1);currentDate=dateToKey(d);renderAll();}
function prevPoidsDay(){const d=new Date(poidsDate+'T12:00:00');d.setDate(d.getDate()-1);poidsDate=dateToKey(d);renderMain();}
function nextPoidsDay(){if(poidsDate>=todayKey())return;const d=new Date(poidsDate+'T12:00:00');d.setDate(d.getDate()+1);poidsDate=dateToKey(d);renderMain();}
function addFood(){const data=getMealData();const meal=MEALS[currentMeal];const cq=parseFloat(document.getElementById('qty-input')?.value)||1;let item;if(mode==='custom'){const n=document.getElementById('c-name')?.value.trim();const p=parseFloat(document.getElementById('c-p')?.value);const l=parseFloat(document.getElementById('c-l')?.value);const g=parseFloat(document.getElementById('c-g')?.value)||0;const fi=parseFloat(document.getElementById('c-fi')?.value)||0;if(!n||isNaN(p)||isNaN(l))return;const cf=loadCustomFoods();if(!cf.find(f=>f.name===n)){cf.push({name:n,p,l,g,f:fi});saveCustomFoods(cf);}item={name:n,p:r1(p*cq),l:r1(l*cq),g:r1(g*cq),f:r1(fi*cq),baseP:p,baseL:l,baseG:g,baseF:fi,qty:cq};}else{if(selectedFoodIdx===null)return;const f=getAllFoods()[selectedFoodIdx];item={name:f.name,p:r1(f.p*cq),l:r1(f.l*cq),g:r1((f.g||0)*cq),f:r1((f.f||0)*cq),baseP:f.p,baseL:f.l,baseG:f.g||0,baseF:f.f||0,qty:cq};incrementUsage(f.name);}const prevTot=dayTotals(data);data[meal].push(item);saveDay(currentDate,data);lastAdded={meal,idx:data[meal].length-1};qty=1;const newTot=dayTotals(data);if(prevTot.p<PROT_TARGET()&&newTot.p>=PROT_TARGET()&&navigator.vibrate)navigator.vibrate([100,50,200]);renderAll();if(mode==='list'&&selectedFoodIdx!==null){setTimeout(()=>{const el=document.querySelector('.food-list-item[data-idx="'+selectedFoodIdx+'"]');if(el)el.classList.add('selected');},50);}}
function undoLast(){if(!lastAdded)return;const data=getMealData();data[lastAdded.meal].splice(lastAdded.idx,1);saveDay(currentDate,data);lastAdded=null;renderAll();}
function removeFood(mealName,idx){showModal('Supprimer cet aliment ?',()=>{const data=getMealData();data[mealName].splice(idx,1);saveDay(currentDate,data);lastAdded=null;renderAll();});}
function editQty(mealName,idx){const data=getMealData();const item=data[mealName][idx];qtyEditTarget={mealName,idx};document.getElementById('qty-modal-input').value=item.qty||1;document.getElementById('qty-modal').style.display='flex';}
function confirmQtyEdit(){if(!qtyEditTarget)return;const nq=parseFloat(document.getElementById('qty-modal-input').value)||1;const data=getMealData();const item=data[qtyEditTarget.mealName][qtyEditTarget.idx];item.p=r1((item.baseP||item.p)*nq);item.l=r1((item.baseL||item.l)*nq);item.g=r1((item.baseG||0)*nq);item.f=r1((item.baseF||0)*nq);item.qty=nq;saveDay(currentDate,data);document.getElementById('qty-modal').style.display='none';qtyEditTarget=null;renderAll();}
function addFavorite(fi){const fav=loadFavorites()[fi];const data=getMealData();const meal=MEALS[currentMeal];fav.items.forEach(it=>{data[meal].push({...it});incrementUsage(it.name);});saveDay(currentDate,data);showToast('✓ '+fav.name+' ajouté !');renderAll();}
function saveCurrentMealAsFav(){const data=getMealData();const items=data[MEALS[currentMeal]];if(!items.length){alert('Ajoute des aliments d\'abord.');return;}pendingFavItems=items.map(i=>({...i}));document.getElementById('fav-modal-name').value='';document.getElementById('fav-modal').style.display='flex';}
function confirmSaveFav(){const name=document.getElementById('fav-modal-name').value.trim();if(!name)return;const favs=loadFavorites();favs.push({name,items:pendingFavItems});saveFavorites(favs);document.getElementById('fav-modal').style.display='none';pendingFavItems=null;showToast('✓ Favori sauvegardé !');renderAll();}
function deleteFavorite(idx){showModal('Supprimer ce favori ?',()=>{const favs=loadFavorites();favs.splice(idx,1);saveFavorites(favs);renderAll();});}
function deleteFoodFromList(name,idx){const row=document.querySelector('.food-list-item[data-idx="'+idx+'"]');if(!row)return;const existing=document.querySelector('.food-action-opts');if(existing)existing.remove();if(row.dataset.optOpen){delete row.dataset.optOpen;return;}row.dataset.optOpen='1';const opts=document.createElement('div');opts.className='food-action-opts';opts.style.cssText='display:flex;gap:6px;padding:6px 12px;background:#1a2535;border-top:1px solid #252d3d;';const btnEdit=document.createElement('button');btnEdit.textContent='✎ Modifier';btnEdit.style.cssText='flex:1;padding:6px;background:#2a3f5a;color:#8ab0d0;border:none;border-radius:6px;font-size:11px;font-family:Poppins,sans-serif;font-weight:600;cursor:pointer;';btnEdit.onclick=function(){editFoodFromList(name,idx);};const btnDel=document.createElement('button');btnDel.textContent='🗑 Supprimer';btnDel.style.cssText='flex:1;padding:6px;background:#3a1a1a;color:#e85a4a;border:none;border-radius:6px;font-size:11px;font-family:Poppins,sans-serif;font-weight:600;cursor:pointer;';btnDel.onclick=function(){confirmDeleteFood(name);};opts.appendChild(btnEdit);opts.appendChild(btnDel);row.parentElement.insertBefore(opts,row.nextSibling);}
function saveEditedFood(){if(!editingFood)return;const n=document.getElementById('c-name')?.value.trim();const p=parseFloat(document.getElementById('c-p')?.value);const l=parseFloat(document.getElementById('c-l')?.value);const g=parseFloat(document.getElementById('c-g')?.value)||0;const fi=parseFloat(document.getElementById('c-fi')?.value)||0;if(!n||isNaN(p)||isNaN(l)){alert('Remplis tous les champs obligatoires.');return;}deleteFoodFn(editingFood.name);const cf=loadCustomFoods();cf.push({name:n,p,l,g,f:fi});saveCustomFoods(cf);editingFood=null;mode='list';renderAll();showToast('✓ Aliment modifié !');}
function confirmDeleteFood(name){showModal('Supprimer "'+name+'" de la liste ?',()=>{deleteFoodFn(name);selectedFoodIdx=null;renderAll();});}
function editFoodFromList(name,idx){const foods=getAllFoods();const f=foods[idx];if(!f)return;editingFood={name:f.name,idx};mode='custom';renderMain();setTimeout(()=>{fillCustomForm(f.name,f.p,f.l,f.g||0,f.f||0);},50);}
function fillCustomForm(name,p,l,g,fi){document.getElementById('c-name').value=name;document.getElementById('c-p').value=p;document.getElementById('c-l').value=l;const gEl=document.getElementById('c-g');if(gEl)gEl.value=g||0;const fEl=document.getElementById('c-fi');if(fEl)fEl.value=fi||0;}
function changeQty(delta){const el=document.getElementById('qty-input');if(!el)return;el.value=Math.max(0.1,r1((parseFloat(el.value)||1)+delta));}
function setMode(m){mode=m;foodSearchTerm='';selectedFoodIdx=null;renderMain();}
function handleSearchInput(val){foodSearchTerm=val;clearTimeout(searchDebounce);searchDebounce=setTimeout(()=>{const el=document.getElementById('food-search-input');const pos=el?el.selectionStart:null;renderMain();const newEl=document.getElementById('food-search-input');if(newEl){newEl.focus();if(pos!==null)try{newEl.setSelectionRange(pos,pos);}catch(e){}}},300);}
function manualSave(btn){const data=getMealData();saveDay(currentDate,data);btn.textContent='✓ Enregistré !';btn.style.background='#1a3a1a';btn.style.color='#4caf7d';setTimeout(()=>{btn.textContent='💾 Enregistrer';btn.style.background='#1a2a1a';btn.style.color='#6ab06a';},2000);}
function showToast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2500);}
function saveTargetsInput(){const prot=parseFloat(document.getElementById('tgt-prot')?.value);const gluc=parseFloat(document.getElementById('tgt-gluc')?.value);const fiber=parseFloat(document.getElementById('tgt-fiber')?.value);if(isNaN(prot)||prot<50||prot>400){alert('Objectif protéines invalide');return;}if(isNaN(gluc)||gluc<50||gluc>600){alert('Objectif glucides invalide');return;}if(isNaN(fiber)||fiber<10||fiber>100){alert('Objectif fibres invalide');return;}saveTargets({prot,gluc,fiber});renderAll();showToast('Objectifs mis à jour ✓');}
function saveWeightInputPoids(){const val=parseFloat(document.getElementById('weight-input')?.value);if(isNaN(val)||val<40||val>200){alert('Poids invalide');return;}saveWeightFn(poidsDate,val);const btn=document.querySelector('.weight-save-btn');if(btn){btn.textContent='✓ Sauvegardé !';btn.style.background='#1a3a1a';setTimeout(()=>{btn.textContent='💾 Sauvegarder';btn.style.background='';renderMain();},1800);}else renderMain();}
function saveObjectiveInput(){const val=parseFloat(document.getElementById('obj-input')?.value);if(isNaN(val)||val<50||val>200){alert('Objectif invalide');return;}saveObjectiveFn({target:val});renderAll();showToast('Objectif mis à jour : '+val+'kg ✓');}
function showModal(title,onOk){document.getElementById('modal-title').textContent=title;document.getElementById('modal-confirm').onclick=()=>{closeModal();onOk();};document.getElementById('modal').style.display='flex';}
function closeModal(){document.getElementById('modal').style.display='none';}
function getLipClass(l){return l>LIP_MAX?'lip-alert':l>LIP_WARN?'lip-warn':'lip-ok';}
function getMealClass(l){return l>LIP_MAX?'alert':l>LIP_WARN?'warn':'ok';}
function confirmReset(){showModal('Effacer tous les repas du jour ?',()=>{showModal('Confirmer — irréversible',()=>{saveDay(currentDate,{"Petit-déjeuner":[],"Déjeuner":[],"Collation":[],"Dîner":[]});lastAdded=null;renderAll();});});}

// ══ RENDER HEADER ══
function renderHeader(){
  const data=getMealData();const dt=dayTotals(data);
  const pPct=Math.min((dt.p/PROT_TARGET())*100,100);const gPct=Math.min((dt.g/GLUC_TARGET())*100,100);const ft=FIBER_TARGET();const fPct=Math.min((dt.f/ft)*100,100);
  const pt=PROT_TARGET(),gt=GLUC_TARGET();
  document.getElementById('prog-bars').innerHTML='<div class="prog-row"><span class="prog-icon">💪</span><div class="progress-bar"><div class="progress-fill" style="width:'+pPct+'%;background:#e8c94a"></div></div><span class="prog-val" style="color:#e8c94a">P : '+dt.p.toFixed(0)+'/'+pt+'g</span></div><div class="prog-row"><span class="prog-icon">⚡</span><div class="progress-bar"><div class="progress-fill" style="width:'+gPct+'%;background:#4a8abf"></div></div><span class="prog-val" style="color:#4a8abf">G : '+dt.g.toFixed(0)+'/'+gt+'g</span></div><div class="prog-row"><span class="prog-icon">🌾</span><div class="progress-bar"><div class="progress-fill" style="width:'+fPct+'%;background:#c4982a"></div></div><span class="prog-val" style="color:#c4982a">F : '+dt.f.toFixed(0)+'/'+ft+'g</span></div>';
  document.getElementById('date-label').textContent=formatDate(currentDate);
  document.getElementById('meals-mini').innerHTML=MEALS.map(m=>{const t=mealTotals(data[m]||[]);const lc=t.l>LIP_MAX?'#e85a4a':t.l>LIP_WARN?'#e8c94a':'#e07a7a';return '<div class="meal-mini"><div class="meal-mini-name">'+m.substring(0,5)+'</div><div class="meal-mini-p" style="color:#e8c94a">P:'+t.p.toFixed(0)+'g</div><div class="meal-mini-l" style="color:'+lc+'">L:'+t.l.toFixed(0)+'g</div><div class="meal-mini-g" style="color:#4a8abf">G:'+t.g.toFixed(0)+'g</div><div class="meal-mini-f" style="color:#c4982a">F:'+t.f.toFixed(0)+'g</div></div>';}).join('');
}
function renderTabs(){const data=getMealData();document.getElementById('tabs').innerHTML=MEALS.map((m,i)=>{const t=mealTotals(data[m]||[]);const ind=t.l>LIP_MAX?'<span style="color:#e85a4a">!</span>':t.l>LIP_WARN?'<span style="color:#e8c94a">·</span>':'';const labels=['P-DÉJ','Déjeuner','Collat','Dîner'];return '<button class="tab'+(currentMeal===i?' active':'')+'" onclick="currentMeal='+i+';renderAll()">'+labels[i]+ind+'</button>';}).join('');}

// ══ RENDER REPAS ══
function renderRepas(){
  const data=getMealData();const meal=MEALS[currentMeal];const items=data[meal]||[];const mt=mealTotals(items);const favs=loadFavorites();
  let am='';if(mt.l>LIP_MAX)am='<div class="alert-msg alert">⚠️ Dépasse 15g — prends le Créon mid-meal</div>';else if(mt.l>LIP_WARN)am='<div class="alert-msg warn">⚡ Approche de 15g — surveille la suite</div>';
  let h='<div class="content">';
  if(lastAdded&&lastAdded.meal===meal)h+='<div class="undo-bar"><span class="undo-text">Aliment ajouté</span><button class="undo-btn" onclick="undoLast()">↩ Annuler</button></div>';
  h+='<div class="meal-total '+getMealClass(mt.l)+'"><div class="meal-total-row"><span class="meal-total-name">'+meal+'</span><div class="meal-total-nums"><span class="prot-val">P:'+mt.p.toFixed(1)+'g</span><span class="lip-val '+getLipClass(mt.l)+'">L:'+mt.l.toFixed(1)+'g</span><span class="gluc-val">G:'+mt.g.toFixed(1)+'g</span><span style="font-size:13px;font-weight:700;color:#c4982a">F:'+mt.f.toFixed(1)+'g</span></div></div>'+am+'</div>';
  h+='<button class="save-btn" onclick="manualSave(this)">💾 Enregistrer</button>';
  items.forEach((item,i)=>{h+='<div class="food-item"><div class="food-item-info"><div class="food-item-name">'+item.name+'</div><div class="food-item-macros">P:'+item.p.toFixed(1)+'g · L:'+item.l.toFixed(1)+'g · G:'+(item.g||0).toFixed(1)+'g · F:'+(item.f||0).toFixed(1)+'g · ×'+(item.qty||1)+'</div></div><div class="food-item-actions"><button class="food-item-qty" onclick="editQty(\''+esc(meal)+'\','+i+')">✎</button><button class="food-item-remove" onclick="removeFood(\''+esc(meal)+'\','+i+')">×</button></div></div>';});
  h+='<div class="fav-panel"><div class="fav-header" onclick="favOpen=!favOpen;renderMain()"><span class="fav-header-label">⭐ Repas favoris ('+favs.length+')</span><span class="fav-header-arrow" style="transform:rotate('+(favOpen?'90':'0')+'deg)">▶</span></div>';
  if(favOpen){h+='<div class="fav-body"><div class="fav-grid">';favs.forEach((fav,fi)=>{const fp=fav.items.reduce((s,it)=>s+it.p,0).toFixed(0);const fl=fav.items.reduce((s,it)=>s+it.l,0).toFixed(0);h+='<div class="fav-tag" onclick="addFavorite('+fi+')">'+fav.name+' <span style="font-size:9px;color:#4a6a7a">P:'+fp+'g L:'+fl+'g</span><span class="fav-tag-del" onclick="event.stopPropagation();deleteFavorite('+fi+')">×</span></div>';});h+='</div><button class="fav-add-btn" onclick="saveCurrentMealAsFav()">+ Sauvegarder ce repas</button></div>';}
  h+='</div>';
  h+='<div class="add-panel"><div class="section-title">Ajouter un aliment</div><div class="mode-toggle"><button class="mode-btn'+(mode==='list'?' active':'')+'" onclick="setMode(\'list\')">Fréquents</button><button class="mode-btn'+(mode==='custom'?' active':'')+'" onclick="setMode(\'custom\')">Personnalisé</button></div>';
  if(mode==='list'){const allFoods=getAllFoods();const filtered=foodSearchTerm?allFoods.filter(f=>f.name.toLowerCase().indexOf(foodSearchTerm.toLowerCase())!==-1):allFoods;h+='<input type="text" class="food-search" placeholder="🔍 Rechercher..." value="'+esc(foodSearchTerm)+'" oninput="handleSearchInput(this.value)" id="food-search-input"><div class="food-list">';filtered.slice(0,30).forEach((f,i)=>{const ri=allFoods.indexOf(f);const isSel=ri===selectedFoodIdx;h+='<div class="food-list-item'+(isSel?' selected':'')+'" data-idx="'+ri+'" onclick="selectedFoodIdx='+ri+';document.querySelectorAll(\'.food-list-item\').forEach(e=>e.classList.remove(\'selected\'));this.classList.add(\'selected\')"><span class="food-list-name">'+f.name+'</span><span class="food-list-macros">P:'+f.p+' L:'+f.l+' G:'+(f.g||0)+'g</span><button class="food-list-del" onclick="event.stopPropagation();deleteFoodFromList(\''+esc(f.name)+'\','+ri+')">🗑</button></div>';});h+='</div>';}
  else{const cf=loadCustomFoods();h+='<div><div class="custom-name"><input type="text" id="c-name" placeholder="Nom de l\'aliment"></div><div class="custom-row"><input type="number" id="c-p" placeholder="Protéines (g)" step="0.1"><input type="number" id="c-l" placeholder="Lipides (g)" step="0.1"></div><div style="margin-bottom:8px"><input type="number" id="c-g" placeholder="Glucides (g)" step="0.1"></div><div style="margin-bottom:8px"><input type="number" id="c-fi" placeholder="Fibres (g)" step="0.1"></div></div>';if(cf.length>0){h+='<div class="custom-food-list"><div class="custom-food-header">Mes aliments sauvegardés</div>';cf.forEach(f=>{h+='<span class="custom-food-tag" onclick="fillCustomForm(\''+esc(f.name)+'\','+f.p+','+f.l+','+(f.g||0)+')">'+f.name+' <span style="color:#4a5a6a;font-size:9px">P:'+f.p+' L:'+f.l+'</span><span class="custom-food-del" onclick="event.stopPropagation();deleteFoodFromList(\''+esc(f.name)+'\')">×</span></span>';});h+='</div>';}}
  if(editingFood&&mode==='custom')h+='<div style="margin-top:10px;display:flex;gap:8px"><button onclick="editingFood=null;mode=\'list\';renderMain()" style="flex:1;padding:11px;background:#1e2535;color:#8a9ab0;border:none;border-radius:9px;font-size:12px;cursor:pointer;font-family:Poppins,sans-serif;font-weight:600">✕ Annuler</button><button onclick="saveEditedFood()" style="flex:2;padding:11px;background:linear-gradient(135deg,#2a6a2a,#1a4a1a);color:#e2ddd4;border:none;border-radius:9px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif">✓ Enregistrer</button></div></div>';
  else h+='<div class="qty-row"><div class="qty-ctrl"><button class="qty-btn" onclick="changeQty(-0.5)">−</button><input type="number" id="qty-input" class="qty-input" value="'+qty+'" step="0.1" min="0.1" onchange="qty=parseFloat(this.value)||1"><button class="qty-btn" onclick="changeQty(0.5)">+</button></div><button class="add-btn" onclick="addFood()">+ Ajouter</button></div></div>';
  h+='<button style="margin-top:10px;width:100%;padding:10px;background:transparent;color:#3a2a2a;border:1px solid #2a1a1a;border-radius:9px;font-size:11px;cursor:pointer;font-family:Poppins,sans-serif;font-weight:500" onclick="confirmReset()">Réinitialiser la journée</button></div>';
  return h;
}

// ══ RENDER MUSCU ══
function renderMuscu(){
  if(muscuSubView==='session')return renderMuscuSession();
  if(muscuSubView==='group'&&muscuGroupId)return renderMuscuGroup(muscuGroupId);
  if(muscuSubView==='perso')return renderMuscuPerso();
  if(muscuSubView==='alea')return renderMuscuAlea();
  return renderMuscuHome();
}

function renderMuscuHome(){
  const totalSessions=getTotalSessions();const suggestions=getSuggestedGroups();const weekDays=getWeekGymSessionsAt(muscuWeekOffset);
  const tractionsRecord=getTractionsRecord();const dayNames=['L','M','M','J','V','S','D'];
  let h='<div class="gym-content">';
  h+='<div class="gym-top-row"><div class="gym-chip"><span class="gym-chip-label">Séances</span><span class="gym-chip-val">'+totalSessions+'</span></div><div class="gym-chip"><span class="gym-chip-label">J+</span><span class="gym-chip-val">'+daysSinceStart()+'</span></div><div class="gym-chip" onclick="openTractionsModal()" style="cursor:pointer;border-color:'+(tractionsRecord?'#4a4a2a':'#1e2535')+';background:'+(tractionsRecord?'#1a1a0d':'#141929')+'"><span style="font-size:11px">🏆</span><span class="gym-chip-val" style="color:#e8c94a;font-size:12px">'+(tractionsRecord?tractionsRecord+' reps':'—')+'</span></div><div class="gym-chip"><span class="gym-chip-label">Sem.</span><span class="gym-chip-val">'+getTractionsWeekCount()+'</span></div></div>';
  h+='<div class="gym-action-row"><button class="gym-action-btn perso" onclick="openPerso()">🎯 Ma séance perso</button><button class="gym-action-btn alea" onclick="openAlea()">🎲 Séance aléatoire</button></div>';
  h+='<button onclick="openPastSessionModal()" style="width:100%;padding:9px;background:transparent;color:#4a5a7a;border:1px dashed #2a3a5a;border-radius:9px;font-size:12px;cursor:pointer;font-family:Poppins,sans-serif;font-weight:600;margin-bottom:10px">+ Ajouter une séance passée</button>';
  if(suggestions.length){
    h+='<div class="gym-suggest" onclick="openGroup(\''+suggestions[0].id+'\')" style="margin-bottom:6px"><div><div class="gym-suggest-tag">⭐ Séance prioritaire</div><div class="gym-suggest-name">'+suggestions[0].icon+' '+suggestions[0].name+'</div></div><span style="color:#4a6a4a;font-size:18px">→</span></div>';
    if(suggestions[1])h+='<div class="gym-suggest" onclick="openGroup(\''+suggestions[1].id+'\')" style="background:#141929;border-color:#1e2535;margin-bottom:10px"><div><div class="gym-suggest-tag" style="color:#4a5a6a">Alternative</div><div class="gym-suggest-name" style="color:#8ab0d0;font-size:12px">'+suggestions[1].icon+' '+suggestions[1].name+'</div></div><span style="color:#3a4a5a;font-size:18px">→</span></div>';
  } else {
    let soonestGroup=null,soonestH=Infinity;
    MUSCLE_GROUPS.forEach(g=>{const r=getRecoveryStatus(g.id);if(r.status!=='green'&&r.remainingH>0&&r.remainingH<soonestH){soonestH=r.remainingH;soonestGroup=g;}});
    const nextMsg=soonestGroup?'<br><span style="color:#e8c94a;font-weight:700;font-size:12px">Prochain disponible : '+soonestGroup.icon+' '+soonestGroup.name+' dans '+soonestH+'h</span>':'';
    h+='<div style="background:#1a1a1a;border:1px solid #1e1e35;border-radius:10px;padding:10px 14px;margin-bottom:10px;text-align:center;font-size:12px;color:#4a4a6a">💤 Tous les groupes en repos'+nextMsg+'</div>';
  }
  const weekLabel=muscuWeekOffset===0?'Cette semaine':muscuWeekOffset===-1?'Semaine dernière':'Semaine du '+formatWeekLabel(weekDays);
  h+='<div style="display:flex;align-items:center;gap:6px;margin-bottom:4px">';
  h+='<button class="date-btn" style="padding:4px 10px" onclick="muscuWeekOffset--;renderMain()">◀</button>';
  h+='<div class="section-title" style="flex:1;margin:0;text-align:center">'+weekLabel+'</div>';
  h+='<button class="date-btn" style="padding:4px 10px;'+(muscuWeekOffset>=0?'opacity:0.3;cursor:default':'')+'" onclick="if(muscuWeekOffset<0){muscuWeekOffset++;renderMain()}">▶</button>';
  h+='</div>';
  h+='<div class="gym-week-row">';
  weekDays.forEach((day,i)=>{const hasSessions=day.sessions.length>0;const mood=hasSessions?day.sessions[day.sessions.length-1].mood:'';const dotColor=hasSessions?(mood==='💪'?'#4caf7d':mood==='😐'?'#e8c94a':'#e85a4a'):'#1e2535';const g=hasSessions?MUSCLE_GROUPS.find(x=>x.id===day.sessions[0].gid):null;const shortName=g?g.name.split('+')[0].trim().substring(0,3):(hasSessions?'Pers':'');h+='<div class="gym-week-day'+(day.isToday?' today':'')+'"><div class="gym-week-day-name">'+dayNames[i]+'</div><div class="gym-week-day-dot" style="background:'+dotColor+'"></div><div class="gym-week-day-label" style="color:'+(hasSessions?dotColor:'#2a3a4a')+'">'+( hasSessions?shortName:'—')+'</div></div>';});
  h+='</div>';
  h+='<div class="section-title" style="margin-top:6px">Groupes musculaires</div>';
  MUSCLE_GROUPS.forEach(g=>{const rec=getRecoveryStatus(g.id);const lastSession=getLastSession(g.id);const upgrade=hasUpgrade(g.id);const isIdle=lastSession&&rec.hoursAgo!==null&&rec.hoursAgo>5*24&&rec.status==='green';h+='<div class="gym-card" onclick="openGroup(\''+g.id+'\')" ><div class="gym-card-top"><div><div class="gym-card-name">'+g.icon+' '+g.name+'</div></div><div class="gym-card-right"><div class="gym-rec-dot gym-rec-'+rec.status+'"></div><div class="gym-rec-label '+rec.status+'" style="white-space:nowrap">'+(rec.sublabel?rec.label+' · '+rec.sublabel:rec.label)+'</div>'+'</div></div><div class="gym-card-bottom">';if(rec.daysAgo!==null)h+='<span class="gym-days-ago">Il y a '+rec.daysAgo+' j</span>';if(lastSession)h+='<span class="gym-mood-badge">'+lastSession.mood+'</span>';if(rec.linkedUsed)h+='<span class="gym-linked-badge">via '+rec.linkedName+'</span>';if(upgrade)h+='<span class="gym-upgrade-badge">⬆️ Amélioré</span>';if(isIdle)h+='<span class="gym-idle-badge">⚠️ '+Math.floor(rec.hoursAgo/24)+'j sans séance</span>';h+='</div></div>';});
  h+='</div>';return h;
}

function renderMuscuGroup(gid){
  const g=MUSCLE_GROUPS.find(x=>x.id===gid);
  if(!g)return '<div class="gym-content"><button class="gym-back-btn" onclick="backToMuscu()">← Retour</button><p>Groupe introuvable</p></div>';
  const program=getGroupProgram(gid);const rec=getRecoveryStatus(gid);const recHours=getRecovery(gid);
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="backToMuscu()">← Retour</button>';
  h+='<div class="gym-group-title">'+g.icon+' '+g.name+'</div>';

  // ✅ NOUVEAU BLOC RÉCUP ENRICHI
  let recMainText='',recSubText='';
  const dotClass='gym-rec-block-dot gym-rec-'+rec.status;
  if(rec.hoursAgo===null){
    recMainText='<span style="color:#4caf7d;font-size:14px;font-weight:700">Jamais fait — Prêt ✓</span>';
    recSubText='';
  } else if(rec.status==='green'){
    const readySinceH=Math.max(0,Math.floor(rec.hoursAgo-recHours));
    recMainText='<span style="color:#4caf7d;font-size:14px;font-weight:700">Prêt ✓</span>';
    recSubText='Ouvert depuis '+readySinceH+'h'+(rec.linkedUsed?' · via '+rec.linkedName:'');
  } else {
    const remainH=Math.ceil(rec.effectiveRec-rec.hoursAgo);
    const color=rec.status==='orange'?'#e8c94a':'#e85a4a';
    recMainText='<span style="color:'+color+';font-size:14px;font-weight:700">Encore '+remainH+'h de récupération</span>';
    recSubText=(rec.linkedUsed?'Déclenché via '+rec.linkedName+' · ':'')+(rec.daysAgo!==null?'Il y a '+rec.daysAgo+'j':'');
  }
  h+='<div class="gym-rec-block"><div class="'+dotClass+'"></div><div class="gym-rec-block-info">'+recMainText+(recSubText?'<div class="gym-rec-block-sub">'+recSubText+'</div>':'')+'</div><button class="gym-rec-edit-btn" onclick="openRecModal(\''+gid+'\')">⏱ '+recHours+'h ✎</button></div>';

  h+='<div class="gym-section-label">Échauffement</div>';
  g.warmup.forEach(ex=>{h+='<div class="gym-ex-card gym-ex-warmup"><div class="gym-ex-row"><span class="gym-ex-name" style="color:#7a7ab0">'+ex.name+(ex.equipment?'<span style="font-size:9px;color:#4a4a7a;margin-left:6px">'+ex.equipment+'</span>':'')+'</span><div class="gym-ex-meta"><span class="gym-ex-val" style="color:#5a5a9a">'+ex.sets+'×'+ex.reps+(ex.unit==='sec'?'s':'')+'</span><button class="gym-icon-btn" onclick="showExInfo(\''+esc(ex.name)+'\',\''+esc(ex.info)+'\')">ℹ️</button></div></div></div>';});
  h+='<div class="gym-section-label">Programme <span style="font-size:10px;color:#3a4a5a;font-weight:500">('+program.length+' exercices)</span></div>';
  program.forEach((ex,idx)=>{const eqDisplay=fmtEquipment(ex);h+='<div class="gym-ex-card"><div class="gym-ex-row"><div style="display:flex;flex-direction:column;gap:2px;margin-right:4px"><button class="gym-icon-btn order" onclick="moveEx(\''+gid+'\',\''+ex.id+'\',-1)" style="font-size:11px;padding:0 2px">↑</button><button class="gym-icon-btn order" onclick="moveEx(\''+gid+'\',\''+ex.id+'\',1)" style="font-size:11px;padding:0 2px">↓</button></div><span class="gym-ex-name">'+ex.name+(eqDisplay?'<br><span style="font-size:9px;color:#4a5a6a">'+eqDisplay+'</span>':'')+'</span><div class="gym-ex-meta"><div style="display:flex;flex-direction:column;align-items:center;gap:1px"><span style="font-size:7px;color:#3a4a5a;font-weight:700">SÉR</span><div class="gym-ex-ctrl"><button class="gym-ctrl-btn" onclick="event.stopPropagation();adjustEx(\''+gid+'\',\''+ex.id+'\',\'sets\',-1)">−</button><span class="gym-ex-val">'+ex.sets+'</span><button class="gym-ctrl-btn" onclick="event.stopPropagation();adjustEx(\''+gid+'\',\''+ex.id+'\',\'sets\',1)">+</button></div></div><div style="display:flex;flex-direction:column;align-items:center;gap:1px"><span style="font-size:7px;color:#3a4a5a;font-weight:700">'+(ex.unit==='sec'?'SEC':'REPS')+'</span><div class="gym-ex-ctrl"><button class="gym-ctrl-btn" onclick="event.stopPropagation();adjustEx(\''+gid+'\',\''+ex.id+'\',\'reps\',-1)">−</button><span class="gym-ex-val">'+ex.reps+'</span><button class="gym-ctrl-btn" onclick="event.stopPropagation();adjustEx(\''+gid+'\',\''+ex.id+'\',\'reps\',1)">+</button></div></div><button class="gym-icon-btn" onclick="event.stopPropagation();showExInfo(\''+esc(ex.name)+'\',\''+esc(ex.info||'')+'\')">ℹ️</button><button class="gym-icon-btn edit" onclick="event.stopPropagation();openExEditModal(\''+gid+'\',\''+ex.id+'\')">✎</button></div></div></div>';});
  h+='<button class="gym-add-ex-btn" onclick="openLibModal(\''+gid+'\')">+ Ajouter un exercice</button>';
  h+='<button class="gym-start-btn" onclick="startSession(\''+gid+'\')">▶ Démarrer la séance</button>';
  h+='<button class="gym-reset-btn" onclick="resetGroupProgram(\''+gid+'\')">↺ Revenir au programme par défaut</button>';
  h+='</div>';return h;
}

// ✅ RENDER SESSION — avec validation exercice par exercice + barre de progression
function renderMuscuSession(){
  const gid=muscuGroupId;const isPerso=gid==='_perso'||gid==='_alea';
  const g=isPerso?null:MUSCLE_GROUPS.find(x=>x.id===gid);
  const program=isPerso?persoExercises:getGroupProgram(gid);
  const groupName=gid==='_perso'?'🎯 Séance perso':gid==='_alea'?'🎲 Séance aléatoire':(g?g.icon+' '+g.name:'Séance');
  const doneCount=program.filter(ex=>sessionChecked.has(ex.id)).length;
  const pct=program.length>0?Math.round((doneCount/program.length)*100):0;
  let h='<div class="session-wrap">';
  h+='<div class="session-top"><div class="session-group-name">'+groupName+'</div><button class="session-exit" onclick="exitSession()">✕ Quitter</button></div>';
  // Barre de progression
  h+='<div class="session-progress-label">'+doneCount+' / '+program.length+' exercices</div>';
  h+='<div class="session-progress-bar"><div class="session-progress-fill" style="width:'+pct+'%"></div></div>';
  if(!isPerso&&g&&g.warmup){
    h+='<div class="section-title" style="color:#5a5a9a">Échauffement</div>';
    g.warmup.forEach(ex=>{h+='<div class="session-ex-item session-ex-warmup"><div class="session-ex-row"><span class="session-ex-name" style="color:#7a7ab0;font-size:12px">'+ex.name+'</span><span style="font-size:12px;color:#5a5a9a;font-weight:700">'+ex.sets+'×'+ex.reps+(ex.unit==='sec'?'s':'')+'</span><button class="gym-icon-btn" onclick="showExInfo(\''+esc(ex.name)+'\',\''+esc(ex.info)+'\')">ℹ️</button></div></div>';});
  }
  h+='<div class="section-title" style="margin-top:12px">Programme</div>';
  program.forEach((ex,idx)=>{
    const done=sessionChecked.has(ex.id);
    const setsDelta=isPerso?'adjustPersoEx('+idx+',\'sets\',-1)':'adjustEx(\''+gid+'\',\''+ex.id+'\',\'sets\',-1)';
    const setsPlus=isPerso?'adjustPersoEx('+idx+',\'sets\',1)':'adjustEx(\''+gid+'\',\''+ex.id+'\',\'sets\',1)';
    const repsMinus=isPerso?'adjustPersoEx('+idx+',\'reps\',-1)':'adjustEx(\''+gid+'\',\''+ex.id+'\',\'reps\',-1)';
    const repsPlus=isPerso?'adjustPersoEx('+idx+',\'reps\',1)':'adjustEx(\''+gid+'\',\''+ex.id+'\',\'reps\',1)';
    const eqDisplay=fmtEquipment(ex);
    h+='<div class="session-ex-item'+(done?' ex-done':'')+'"><div class="session-ex-row">';
    // Bouton check
    h+='<button class="session-check-btn'+(done?' done':'')+'" onclick="toggleExCheck(\''+ex.id+'\')">'+(done?'✓':'○')+'</button>';
    h+='<div style="flex:1"><span class="session-ex-name"'+(done?' style="text-decoration:line-through;color:#4a6a4a"':'')+'>'+ex.name+'</span>'+(eqDisplay?'<div style="font-size:9px;color:#4a5a6a;margin-top:1px">'+eqDisplay+'</div>':'')+'</div>';
    h+='<div class="session-ex-ctrl"><button class="session-ctrl-btn" onclick="'+setsDelta+'">−</button><span class="session-ctrl-val" style="font-size:10px;color:#4a6a8a">S:'+ex.sets+'</span><button class="session-ctrl-btn" onclick="'+setsPlus+'">+</button></div>';
    h+='<div class="session-ex-ctrl"><button class="session-ctrl-btn" onclick="'+repsMinus+'">−</button><span class="session-ctrl-val">'+ex.reps+(ex.unit==='sec'?'s':'')+'</span><button class="session-ctrl-btn" onclick="'+repsPlus+'">+</button></div>';
    if(ex.info)h+='<button class="gym-icon-btn" onclick="showExInfo(\''+esc(ex.name)+'\',\''+esc(ex.info)+'\')">ℹ️</button>';
    h+='</div></div>';
  });
  h+='<button class="session-end-btn" onclick="endSession()">✓ Terminer la séance</button>';
  h+='</div>';return h;
}

function renderMuscuPerso(){
  const savedList=loadPersoList();
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="backToMuscu()">← Retour</button>';
  h+='<div class="gym-group-title">🎯 Ma séance perso</div>';
  if(savedList.length){
    h+='<div class="gym-section-label">Séances sauvegardées</div>';
    savedList.forEach(s=>{h+='<div class="perso-saved-item"><div onclick="loadPersoSession(\''+s.id+'\')"><div class="perso-saved-name">'+s.name+'</div><div class="perso-saved-count">'+s.exercises.length+' exercices</div></div><button class="perso-del-btn" onclick="deletePersoSession(\''+s.id+'\')">🗑</button></div>';});
    h+='<div style="margin:10px 0;border-top:1px solid #1e2535"></div>';
  }
  h+='<div class="gym-section-label">Construire une nouvelle séance</div>';
  h+='<input type="text" class="perso-name-input" placeholder="Nom de la séance..." value="'+esc(persoName)+'" onchange="persoName=this.value" oninput="persoName=this.value">';
  if(persoExercises.length){
    persoExercises.forEach((ex,i)=>{
      h+='<div class="perso-ex-item"><div style="display:flex;flex-direction:column;gap:2px;margin-right:4px"><button class="gym-icon-btn order" onclick="movePersoEx('+i+',-1)" style="font-size:11px;padding:0 2px">↑</button><button class="gym-icon-btn order" onclick="movePersoEx('+i+',1)" style="font-size:11px;padding:0 2px">↓</button></div>';
      h+='<div style="flex:1"><div class="perso-ex-name">'+ex.name+'</div><div class="perso-ex-info">'+(ex.groupTarget?'['+ex.groupTarget+'] ':'')+ex.sets+'×'+ex.reps+(ex.unit==='sec'?'s':'')+(ex.equipment?' · '+ex.equipment:'')+'</div></div>';
      h+='<div class="gym-ex-ctrl" style="margin-right:4px"><button class="gym-ctrl-btn" onclick="adjustPersoEx('+i+',\'sets\',-1)">−</button><span class="gym-ex-val" style="font-size:10px">S:'+ex.sets+'</span><button class="gym-ctrl-btn" onclick="adjustPersoEx('+i+',\'sets\',1)">+</button></div>';
      h+='<div class="gym-ex-ctrl" style="margin-right:4px"><button class="gym-ctrl-btn" onclick="adjustPersoEx('+i+',\'reps\',-1)">−</button><span class="gym-ex-val">'+ex.reps+(ex.unit==='sec'?'s':'')+'</span><button class="gym-ctrl-btn" onclick="adjustPersoEx('+i+',\'reps\',1)">+</button></div>';
      h+='<button class="perso-remove-btn" onclick="removePersoEx('+i+')">×</button></div>';
    });
  } else h+='<div style="background:#141929;border:1px dashed #1e2535;border-radius:10px;padding:20px;text-align:center;margin-bottom:10px"><div style="font-size:13px;color:#4a5a6a;margin-bottom:6px">Aucun exercice</div><div style="font-size:11px;color:#3a4a5a">Appuie sur + pour ajouter depuis la bibliothèque</div></div>';
  h+='<button class="gym-add-ex-btn" onclick="openPersoLib()">+ Ajouter depuis la bibliothèque</button>';
  if(persoExercises.length){h+='<button style="width:100%;padding:10px;border-radius:9px;margin-top:6px;background:#1a3a1a;color:#4caf7d;border:1px solid #2a5a2a;font-family:Poppins,sans-serif;font-weight:600;font-size:12px;cursor:pointer" onclick="savePerso()">💾 Sauvegarder cette séance</button>';h+='<button class="gym-start-btn" onclick="startPersoSession()">▶ Démarrer maintenant</button>';}
  h+='</div>';return h;
}

function renderMuscuAlea(){
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="backToMuscu()">← Retour</button><div class="gym-group-title">🎲 Séance aléatoire</div>';
  h+='<div style="font-size:12px;color:#6a7a8a;margin-bottom:14px">Les exercices récemment faits (24h) sont exclus automatiquement.</div>';
  h+='<div class="gym-section-label">Type de séance</div><div class="alea-type-row">';
  h+='<button class="alea-type-btn'+(aleaType==='balanced'?' active':'')+'" onclick="aleaType=\'balanced\';aleaSession=null;renderMain()"><div class="alea-type-title">⚖️ Équilibrée</div><div class="alea-type-sub">Un exercice par groupe, dans un ordre aléatoire</div></button>';
  h+='<button class="alea-type-btn'+(aleaType==='duration'?' active':'')+'" onclick="aleaType=\'duration\';aleaSession=null;renderMain()"><div class="alea-type-title">⏱ Par durée</div><div class="alea-type-sub">Choisis la durée, l\'app calcule le nombre d\'exercices</div></button>';
  h+='<button class="alea-type-btn'+(aleaType==='group'?' active':'')+'" onclick="aleaType=\'group\';aleaSession=null;renderMain()"><div class="alea-type-title">🎯 Par groupe</div><div class="alea-type-sub">Exercices aléatoires dans un groupe musculaire choisi</div></button>';
  h+='</div>';
  if(aleaType==='duration'){const count=Math.max(3,Math.round(aleaDuration*0.2));h+='<div class="slider-wrap"><div class="slider-label">Durée : '+aleaDuration+' minutes</div><input type="range" min="15" max="90" step="5" value="'+aleaDuration+'" oninput="aleaDuration=parseInt(this.value);aleaSession=null;document.querySelector(\'.slider-label\').textContent=\'Durée : \'+aleaDuration+\' minutes\'"></div><div style="font-size:11px;color:#4a5a6a;text-align:center;margin-bottom:10px">≈ '+count+' exercices</div>';}
  if(aleaType==='group'){h+='<select class="group-select" onchange="aleaGroupId=this.value;aleaSession=null"><option value="">— Choisir un groupe —</option>';MUSCLE_GROUPS.forEach(g=>{h+='<option value="'+g.id+'"'+(aleaGroupId===g.id?' selected':'')+'>'+g.icon+' '+g.name+'</option>';});h+='</select>';}
  if(aleaType&&(aleaType!=='group'||aleaGroupId))h+='<button onclick="generateAlea()" style="width:100%;padding:12px;background:linear-gradient(135deg,#2a1a4a,#1a0d30);color:#8a6abf;border:1px solid #3a2a6a;border-radius:12px;font-size:14px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif;margin-bottom:14px">🎲 Générer la séance</button>';
  if(aleaSession&&aleaSession.length){h+='<div class="gym-section-label">Séance générée — '+aleaSession.length+' exercices</div>';aleaSession.forEach(ex=>{const exSets=ex.defaultSets||ex.sets||3;const exReps=ex.defaultReps||ex.reps||10;const exUnit=ex.unit||'reps';const exGroup=ex.group?GROUP_NAMES_FR[ex.group]:'';h+='<div class="alea-result-ex"><div class="alea-result-name">'+(ex.name||ex.id)+'</div><div class="alea-result-meta">'+(exGroup?'['+exGroup+'] ':'')+exSets+'×'+exReps+(exUnit==='sec'?'s':'')+(ex.equipment?' · '+ex.equipment:'')+'</div></div>';});h+='<button onclick="startAleaSession()" style="width:100%;padding:14px;background:linear-gradient(135deg,#1a3a1a,#0d2a0d);color:#4caf7d;border:1px solid #2a5a2a;border-radius:12px;font-size:15px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif;margin-top:10px">▶ Démarrer cette séance</button>';}
  else if(aleaSession&&!aleaSession.length)h+='<div style="background:#1a1a1a;border:1px solid #1e1e35;border-radius:10px;padding:14px;text-align:center;font-size:12px;color:#6a5a4a">Tous les exercices ont été faits récemment. Réessaie dans quelques heures.</div>';
  h+='</div>';return h;
}

// ══ RENDER RECUP ══
function renderRecup(){
  if(recupSessionActive)return renderRecupSession();
  if(recupSubView==='library')return renderRecupLibrary();
  if(recupSubView==='prog')return renderRecupProg();
  if(recupSubView==='perso')return renderRecupPerso();
  if(recupSubView==='alea')return renderRecupAlea();
  return renderRecupHome();
}

function getRecupSuggest(){
  const tired=MUSCLE_GROUPS.filter(g=>{const r=getRecoveryStatus(g.id);return r.status==='red'||r.status==='orange';});
  if(!tired.length)return null;
  const progIds=new Set(),exIds=[];
  tired.forEach(g=>{
    const s=RECUP_MUSCLE_SUGGEST[g.id];
    if(s){s.progs.forEach(p=>progIds.add(p));s.exs.forEach(e=>{if(!exIds.includes(e))exIds.push(e);});}
  });
  return{tired,progs:[...progIds].slice(0,2),exs:exIds.slice(0,3)};
}

function renderRecupHome(){
  const log=loadRecupLog();const sessions=loadRecupSessions();
  const allLog=[...sessions,...log].sort((a,b)=>new Date(b.date)-new Date(a.date));
  const suggest=getRecupSuggest();
  let h='<div class="content">';

  // Contexte muscu — suggestion intelligente
  if(suggest){
    const tiredNames=suggest.tired.map(g=>g.icon+' '+g.name).join(', ');
    h+='<div class="recup-suggest-box"><div class="recup-suggest-title">💡 Suggestion selon ta récup muscu</div>';
    h+='<div style="font-size:11px;color:#8a8a4a;margin-bottom:8px"><b style="color:#e8c94a">En récup :</b> '+tiredNames+'</div>';
    if(suggest.progs.length){
      suggest.progs.forEach(pid=>{const p=RECUP_PROGRAMS.find(x=>x.id===pid);if(p)h+='<div class="recup-suggest-item" onclick="openRecupProg(\''+p.id+'\')" style="cursor:pointer;display:flex;align-items:center;gap:6px;margin-bottom:4px"><span style="font-size:14px">'+p.icon+'</span><span style="color:#8ab0d0;text-decoration:underline">'+p.name+'</span></div>';});
    }
    if(suggest.exs.length){
      h+='<div style="font-size:10px;color:#4a5a6a;margin-top:6px;margin-bottom:4px;font-weight:700;text-transform:uppercase;letter-spacing:1px">Exercices recommandés</div>';
      suggest.exs.forEach(eid=>{const e=RECUP_LIBRARY.find(x=>x.id===eid);if(e){const cc=RECUP_CAT[e.cat]||{color:'#6a7a8a',label:e.cat};h+='<div class="recup-suggest-item" style="color:'+cc.color+'">'+e.name+'</div>';}});
    }
    h+='</div>';
  } else {
    h+='<div style="background:#0d1a0d;border:1px solid #1a3a1a;border-left:3px solid #4caf7d;border-radius:10px;padding:10px 14px;margin-bottom:12px;font-size:11px;color:#4caf7d">✓ Tous les groupes musculaires sont prêts</div>';
  }

  // Navigation 4 boutons
  h+='<div class="recup-nav-grid">';
  h+='<div class="recup-nav-card" onclick="recupSubView=\'library\';renderMain()"><div class="recup-nav-card-icon">📚</div><div class="recup-nav-card-label">Bibliothèque</div><div class="recup-nav-card-sub">'+RECUP_LIBRARY.length+' exercices</div></div>';
  h+='<div class="recup-nav-card" onclick="recupSubView=\'alea\';renderMain()"><div class="recup-nav-card-icon">🎲</div><div class="recup-nav-card-label">Aléatoire</div><div class="recup-nav-card-sub">Génère une séance</div></div>';
  h+='<div class="recup-nav-card" onclick="recupSubView=\'perso\';renderMain()"><div class="recup-nav-card-icon">🎯</div><div class="recup-nav-card-label">Perso</div><div class="recup-nav-card-sub">Construis ta séance</div></div>';
  h+='<div class="recup-nav-card" onclick="scrollToRecupLog()"><div class="recup-nav-card-icon">📊</div><div class="recup-nav-card-label">Historique</div><div class="recup-nav-card-sub">'+(allLog.length)+' entrées</div></div>';
  h+='</div>';

  // Programmes
  h+='<div class="section-title">Programmes</div>';
  RECUP_PROGRAMS.forEach(prog=>{
    h+='<div class="recup-prog-card" style="border-left-color:'+prog.color+'" onclick="openRecupProg(\''+prog.id+'\')">';
    h+='<div class="recup-prog-header"><span class="recup-prog-icon">'+prog.icon+'</span><div class="recup-prog-info"><div class="recup-prog-name">'+prog.name+'</div><div class="recup-prog-meta">⏱ '+prog.duration+' · '+prog.exercises.length+' exercices</div></div><span style="color:#3a4a5a;font-size:16px">›</span></div>';
    h+='<div class="recup-prog-desc">'+prog.description+'</div>';
    h+='</div>';
  });

  // Activités rapides (ancien système conservé avec nouveau design)
  h+='<div class="section-title" style="margin-top:8px">Activités rapides</div>';
  h+='<div class="recup-legend"><div class="recup-legend-item"><span class="recup-log-dot" style="background:#4caf7d;width:9px;height:9px;border-radius:50%;display:inline-block"></span>Libre</div><div class="recup-legend-item"><span class="recup-log-dot" style="background:#e8c94a;width:9px;height:9px;border-radius:50%;display:inline-block"></span>Légère sollicitation</div><div class="recup-legend-item"><span class="recup-log-dot" style="background:#e85a4a;width:9px;height:9px;border-radius:50%;display:inline-block"></span>Déconseillé</div></div>';
  const recs=getRecupRecommendations();
  recs.forEach(act=>{
    const cls=act.conflicts.length===0?'green':act.conflicts.length===1?'orange':'red';
    const dotColor=act.conflicts.length===0?'#4caf7d':act.conflicts.length===1?'#e8c94a':'#e85a4a';
    h+='<div class="recup-activity '+cls+'">';
    h+='<div class="recup-activity-header"><div class="recup-activity-dot" style="background:'+dotColor+'"></div><span class="recup-activity-name">'+act.name+'</span></div>';
    h+='<div class="recup-benefit">'+act.benefit+'</div>';
    h+='<div class="recup-footer"><span class="recup-duration">⏱ '+act.duration+'</span><button class="recup-log-btn" onclick="logRecupActivity(\''+act.id+'\')">+ Enregistrer</button></div>';
    h+='</div>';
  });

  // Historique
  h+='<div class="section-title" style="margin-top:16px" id="recup-log-anchor">Historique récup</div>';
  if(allLog.length){
    h+='<div class="stats-panel">';
    allLog.slice(0,25).forEach(entry=>{
      const d=new Date(entry.date);
      const dateStr=d.getDate()+'/'+(d.getMonth()+1);
      const name=entry.name||entry.activityName||'Séance';
      const dur=entry.duration||'';
      const type=entry.type||'activity';
      const dotColor=type==='session'?'#4a8abf':type==='yoga'?'#bf9a4a':type==='stretch'?'#4a8abf':type==='mobilite'?'#6ab06a':'#4caf7d';
      h+='<div class="recup-log-row"><div class="recup-log-dot" style="background:'+dotColor+'"></div><span class="recup-log-date">'+dateStr+'</span><span class="recup-log-name">'+name+'</span><span class="recup-log-dur">'+dur+'</span><button style="background:none;border:none;color:#3a2a2a;cursor:pointer;font-size:16px;padding:0 4px" onclick="deleteRecupEntryAll(\''+entry.id+'\')">×</button></div>';
    });
    if(allLog.length>25)h+='<div style="font-size:10px;color:#3a4a5a;text-align:center;padding:6px 0">+'+(allLog.length-25)+' entrées</div>';
    h+='</div>';
  } else {
    h+='<div style="background:#141929;border:1px solid #1e2535;border-radius:10px;padding:16px;text-align:center;font-size:12px;color:#4a5a6a">Aucune activité enregistrée.<br>Explore les programmes ou la bibliothèque.</div>';
  }
  h+='</div>';return h;
}

function renderRecupLibrary(){
  const ALL_TAGS=[...new Set(RECUP_LIBRARY.flatMap(e=>e.tags||[]))];
  const filters=['all','yoga','stretch','mobilite','⭐','débutant','intermédiaire','avancé','anti-douleur dos','conducteur','réveil','pré-sommeil','post-sport'];
  const filterLabels={'all':'Tout ('+RECUP_LIBRARY.length+')','yoga':'🧘 Yoga','stretch':'🤸 Stretch','mobilite':'🦵 Mobilité','⭐':'⭐ Favoris','débutant':'🟢 Débutant','intermédiaire':'🟡 Intermédiaire','avancé':'🔴 Avancé','anti-douleur dos':'Anti-dos','conducteur':'Conducteur','réveil':'Réveil','pré-sommeil':'Soir','post-sport':'Post-sport'};
  const favIds=loadRecupFavs();
  const filtered=RECUP_LIBRARY.filter(e=>{
    if(recupLibFilter==='⭐')return favIds.includes(e.id);
    if(['yoga','stretch','mobilite'].includes(recupLibFilter)&&e.cat!==recupLibFilter)return false;
    if(['débutant','intermédiaire','avancé'].includes(recupLibFilter)&&e.level!==recupLibFilter)return false;
    if(['anti-douleur dos','conducteur','réveil','pré-sommeil','post-sport'].includes(recupLibFilter)&&!(e.tags||[]).includes(recupLibFilter))return false;
    const srch=recupLibSearch.toLowerCase();
    if(srch&&!e.name.toLowerCase().includes(srch)&&!e.info.toLowerCase().includes(srch))return false;
    return true;
  });
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="recupSubView=\'home\';renderMain()">← Retour</button>';
  h+='<div class="gym-group-title">📚 Bibliothèque</div>';
  h+='<input class="lib-search" placeholder="Rechercher..." value="'+esc(recupLibSearch)+'" oninput="recupLibSearch=this.value;renderMain()" style="margin-bottom:8px">';
  h+='<div class="lib-filter-row">';
  filters.forEach(f=>{h+='<button class="lib-filter-btn'+(recupLibFilter===f?' active':'')+'" onclick="recupLibFilter=\''+f+'\';renderMain()">'+filterLabels[f]+'</button>';});
  h+='</div>';
  if(!filtered.length){h+='<div style="background:#141929;border:1px dashed #1e2535;border-radius:10px;padding:20px;text-align:center;font-size:12px;color:#4a5a6a">Aucun exercice trouvé</div>';}
  filtered.forEach(e=>{
    const cc=RECUP_CAT[e.cat]||{color:'#6a7a8a',bg:'#141929',label:e.cat};
    const lv=RECUP_LEVEL[e.level]||{color:'#6a7a8a',bg:'#141929'};
    const isFav=favIds.includes(e.id);
    const metaStr=(e.reps?e.reps+' reps · ':'')+e.duration+'s'+(e.bilateral?' · ×2 côtés':'');
    h+='<div class="recup-ex-card">';
    h+='<span class="recup-ex-cat" style="color:'+cc.color+';background:'+cc.bg+'">'+cc.label+'</span>';
    h+='<div class="recup-ex-info"><div class="recup-ex-name">'+e.name+'</div>';
    h+='<div class="recup-ex-meta">'+metaStr+'</div>';
    h+='<div class="recup-ex-badges"><span class="recup-badge-level" style="color:'+lv.color+';background:'+lv.bg+'">'+e.level+'</span>'+(e.bilateral?'<span class="recup-badge-bilat">×2 côtés</span>':'')+'</div></div>';
    h+='<button class="recup-fav-btn'+(isFav?' active':'')+'" onclick="toggleRecupFav(\''+e.id+'\');renderMain()">'+(isFav?'⭐':'☆')+'</button>';
    h+='<button class="gym-icon-btn" onclick="showExInfo(\''+esc(e.name)+'\',\''+esc(e.info)+'\')">ℹ️</button>';
    h+='<button class="lib-item-add" onclick="addRecupExToPerso(\''+e.id+'\')">+</button>';
    h+='</div>';
  });
  h+='<div style="margin-top:10px;padding:10px 14px;background:#141929;border-radius:10px;border:1px solid #1e2535;font-size:11px;color:#4a5a6a;text-align:center">⭐ Favoris · ℹ️ Détail · <b style="color:#4caf7d">+</b> Ajouter à séance perso</div>';
  h+='</div>';return h;
}

function renderRecupProg(){
  const prog=RECUP_PROGRAMS.find(p=>p.id===recupProgId);
  if(!prog)return renderRecupHome();
  const exercises=prog.exercises.map(id=>RECUP_LIBRARY.find(e=>e.id===id)).filter(Boolean);
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="recupSubView=\'home\';renderMain()">← Retour</button>';
  h+='<div class="gym-group-title">'+prog.icon+' '+prog.name+'</div>';
  h+='<div style="background:#141929;border:1px solid #1e2535;border-left:3px solid '+prog.color+';border-radius:10px;padding:10px 14px;margin-bottom:12px;font-size:11px;color:#6a7a8a">⏱ '+prog.duration+' · '+exercises.length+' exercices · '+prog.description+'</div>';
  exercises.forEach(e=>{
    const cc=RECUP_CAT[e.cat]||{color:'#6a7a8a',bg:'#141929',label:e.cat};
    const metaStr=(e.reps?e.reps+' reps · ':'')+e.duration+'s'+(e.bilateral?' · ×2 côtés':'');
    h+='<div class="recup-ex-card">';
    h+='<span class="recup-ex-cat" style="color:'+cc.color+';background:'+cc.bg+'">'+cc.label+'</span>';
    h+='<div class="recup-ex-info"><div class="recup-ex-name">'+e.name+'</div><div class="recup-ex-meta">'+metaStr+'</div></div>';
    h+='<button class="gym-icon-btn" onclick="showExInfo(\''+esc(e.name)+'\',\''+esc(e.info)+'\')">ℹ️</button>';
    h+='</div>';
  });
  const progLabel=esc(prog.icon+' '+prog.name);
  h+='<div style="display:flex;gap:8px;margin-top:10px">';
  h+='<button style="flex:1;padding:13px;background:#141929;color:#4a8abf;border:1px solid #2a4a6a;border-radius:12px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif" onclick="startRecupSession(\''+prog.id+'\',\''+progLabel+'\')">▶ Démarrer</button>';
  h+='<button style="flex:1;padding:13px;background:linear-gradient(135deg,#1a3a1a,#0d2a0d);color:#4caf7d;border:1px solid #2a5a2a;border-radius:12px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif" onclick="logRecupSession(\''+prog.id+'\',\''+progLabel+'\',\''+prog.duration+'\')">✓ Déjà fait</button>';
  h+='</div>';
  h+='</div>';return h;
}

function renderRecupPerso(){
  const savedList=loadRecupPersoList();
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="recupSubView=\'home\';renderMain()">← Retour</button>';
  h+='<div class="gym-group-title">🎯 Séance perso</div>';
  if(savedList.length){
    h+='<div class="gym-section-label">Séances sauvegardées</div>';
    savedList.forEach(s=>{h+='<div class="perso-saved-item"><div onclick="loadRecupPersoSession(\''+s.id+'\')"><div class="perso-saved-name">'+s.name+'</div><div class="perso-saved-count">'+s.exercises.length+' exercices · ≈'+calcRecupDuration(s.exercises)+' min</div></div><button class="perso-del-btn" onclick="deleteRecupPersoSession(\''+s.id+'\')">🗑</button></div>';});
    h+='<div style="margin:10px 0;border-top:1px solid #1e2535"></div>';
  }
  h+='<div class="gym-section-label">Construire une nouvelle séance</div>';
  h+='<input type="text" class="perso-name-input" placeholder="Nom de la séance..." value="'+esc(recupPersoName)+'" onchange="recupPersoName=this.value" oninput="recupPersoName=this.value">';
  if(recupPersoExs.length){
    h+='<div style="font-size:11px;color:#4a6a8a;margin-bottom:8px;font-weight:600">≈ '+calcRecupDuration(recupPersoExs)+' min estimées</div>';
    recupPersoExs.forEach((e,i)=>{
      const cc=RECUP_CAT[e.cat]||{color:'#6a7a8a',bg:'#141929',label:e.cat};
      const metaStr=(e.reps?e.reps+' reps · ':'')+e.duration+'s'+(e.bilateral?' · ×2':'');
      h+='<div class="perso-ex-item">';
      h+='<div style="display:flex;flex-direction:column;gap:2px;margin-right:4px"><button class="gym-icon-btn order" onclick="moveRecupPersoEx('+i+',-1)" style="font-size:11px;padding:0 2px">↑</button><button class="gym-icon-btn order" onclick="moveRecupPersoEx('+i+',1)" style="font-size:11px;padding:0 2px">↓</button></div>';
      h+='<span style="font-size:9px;color:'+cc.color+';background:'+cc.bg+';border-radius:4px;padding:2px 5px;margin-right:6px;white-space:nowrap;font-weight:700;flex-shrink:0">'+cc.label+'</span>';
      h+='<div style="flex:1;min-width:0"><div class="perso-ex-name" style="white-space:nowrap;overflow:hidden;text-overflow:ellipsis">'+e.name+'</div><div class="perso-ex-info">'+metaStr+'</div></div>';
      h+='<button class="gym-icon-btn" onclick="showExInfo(\''+esc(e.name)+'\',\''+esc(e.info||'')+'\')">ℹ️</button>';
      h+='<button class="perso-remove-btn" onclick="removeRecupPersoEx('+i+')">×</button>';
      h+='</div>';
    });
  } else {
    h+='<div style="background:#141929;border:1px dashed #1e2535;border-radius:10px;padding:20px;text-align:center;margin-bottom:10px"><div style="font-size:13px;color:#4a5a6a;margin-bottom:6px">Aucun exercice</div><div style="font-size:11px;color:#3a4a5a">Appuie sur + pour ajouter depuis la bibliothèque</div></div>';
  }
  h+='<button class="gym-add-ex-btn" onclick="openRecupLibForPerso()">+ Ajouter depuis la bibliothèque</button>';
  if(recupPersoExs.length){
    h+='<button style="width:100%;padding:10px;border-radius:9px;margin-top:6px;background:#1a3a1a;color:#4caf7d;border:1px solid #2a5a2a;font-family:Poppins,sans-serif;font-weight:600;font-size:12px;cursor:pointer" onclick="saveRecupPerso()">💾 Sauvegarder cette séance</button>';
    h+='<div style="display:flex;gap:8px;margin-top:8px">';
    h+='<button style="flex:1;padding:13px;background:linear-gradient(135deg,#1a3a1a,#0d2a0d);color:#4caf7d;border:1px solid #2a5a2a;border-radius:12px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif" onclick="startRecupSession(null,recupPersoName||\'Séance perso\')">▶ Démarrer</button>';
    h+='<button style="flex:1;padding:13px;background:#141929;color:#6a7a8a;border:1px solid #1e2535;border-radius:12px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif" onclick="logRecupSession(null,recupPersoName||\'Séance perso\',\'≈\'+calcRecupDuration(recupPersoExs)+\' min\')">✓ Déjà fait</button>';
    h+='</div>';
  }
  h+='</div>';return h;
}

function renderRecupAlea(){
  const cats=[{id:'yoga',label:'🧘 Yoga'},{id:'stretch',label:'🤸 Stretching'},{id:'mobilite',label:'🦵 Mobilité'},{id:'mixed',label:'🌀 Mixte'}];
  let h='<div class="gym-content">';
  h+='<button class="gym-back-btn" onclick="recupSubView=\'home\';renderMain()">← Retour</button>';
  h+='<div class="gym-group-title">🎲 Séance aléatoire</div>';
  h+='<div style="font-size:12px;color:#6a7a8a;margin-bottom:14px">Génère une séance selon tes critères du moment.</div>';
  h+='<div class="gym-section-label">Catégorie</div><div class="alea-type-row">';
  cats.forEach(c=>{h+='<button class="alea-type-btn'+(recupAleaCat===c.id?' active':'')+'" onclick="recupAleaCat=\''+c.id+'\';recupAleaResult=null;renderMain()"><div class="alea-type-title">'+c.label+'</div><div class="alea-type-sub">'+(c.id==='mixed'?'Tous types mélangés':RECUP_CAT[c.id]?RECUP_CAT[c.id].label+' uniquement':'')+'</div></button>';});
  h+='</div>';
  h+='<div class="slider-wrap"><div class="slider-label">Durée : '+recupAleaDuration+' minutes</div><input type="range" min="5" max="30" step="5" value="'+recupAleaDuration+'" oninput="recupAleaDuration=parseInt(this.value);recupAleaResult=null;document.querySelector(\'.slider-label\').textContent=\'Durée : \'+recupAleaDuration+\' minutes\'"></div>';
  if(recupAleaCat){
    h+='<button onclick="generateRecupAlea()" style="width:100%;padding:12px;background:linear-gradient(135deg,#1a1a4a,#0d0d30);color:#8a8abf;border:1px solid #2a2a6a;border-radius:12px;font-size:14px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif;margin-bottom:14px">🎲 Générer</button>';
  }
  if(recupAleaResult&&recupAleaResult.length){
    const estMin=calcRecupDuration(recupAleaResult);
    h+='<div class="gym-section-label">Séance générée — '+recupAleaResult.length+' exercices · ≈'+estMin+' min</div>';
    recupAleaResult.forEach(e=>{
      const cc=RECUP_CAT[e.cat]||{color:'#6a7a8a',bg:'#141929',label:e.cat};
      const metaStr=(e.reps?e.reps+' reps · ':'')+e.duration+'s'+(e.bilateral?' · ×2 côtés':'');
      h+='<div class="recup-ex-card"><span class="recup-ex-cat" style="color:'+cc.color+';background:'+cc.bg+'">'+cc.label+'</span><div class="recup-ex-info"><div class="recup-ex-name">'+e.name+'</div><div class="recup-ex-meta">'+metaStr+'</div></div><button class="gym-icon-btn" onclick="showExInfo(\''+esc(e.name)+'\',\''+esc(e.info)+'\')">ℹ️</button></div>';
    });
    h+='<div style="display:flex;gap:8px;margin-top:10px">';
    h+='<button style="flex:1;padding:13px;background:#141929;color:#4a8abf;border:1px solid #2a4a6a;border-radius:12px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif" onclick="startRecupAleaSession()">▶ Démarrer</button>';
    h+='<button style="flex:1;padding:13px;background:linear-gradient(135deg,#1a3a1a,#0d2a0d);color:#4caf7d;border:1px solid #2a5a2a;border-radius:12px;font-size:13px;cursor:pointer;font-weight:700;font-family:Poppins,sans-serif" onclick="logRecupAleaSession()">✓ Déjà fait</button>';
    h+='</div>';
  }
  h+='</div>';return h;
}

function renderRecupSession(){
  const exs=recupSessionExs;
  const doneCount=exs.filter(e=>recupSessionChecked.has(e.id)).length;
  const pct=exs.length>0?Math.round((doneCount/exs.length)*100):0;
  let h='<div class="recup-session-wrap">';
  h+='<div class="recup-session-top"><div class="recup-session-name">'+recupSessionName+'</div><button class="recup-session-exit" onclick="exitRecupSession()">✕ Quitter</button></div>';
  h+='<div class="recup-session-progress-label">'+doneCount+' / '+exs.length+' exercices</div>';
  h+='<div class="recup-session-progress-bar"><div class="recup-session-progress-fill" style="width:'+pct+'%"></div></div>';
  exs.forEach((e,idx)=>{
    const done=recupSessionChecked.has(e.id);
    const cc=RECUP_CAT[e.cat]||{color:'#6a7a8a',bg:'#141929',label:e.cat};
    const metaStr=(e.reps?e.reps+' reps · ':'')+e.duration+'s'+(e.bilateral?' · ×2 côtés':'');
    const timer=recupTimers[e.id];
    h+='<div class="recup-session-item'+(done?' done':'')+'" style="border-left-color:'+cc.border+'">';
    h+='<div class="recup-session-item-row">';
    h+='<button class="recup-check-btn'+(done?' done':'')+'" onclick="toggleRecupCheck(\''+e.id+'\')">'+(done?'✓':'○')+'</button>';
    h+='<span class="recup-ex-cat" style="color:'+cc.color+';background:'+cc.bg+';flex-shrink:0">'+cc.label+'</span>';
    h+='<div style="flex:1;min-width:0"><div style="font-size:12px;font-weight:600;color:'+(done?'#4a6a4a':'#c8d0dc')+(done?';text-decoration:line-through':'')+';white-space:nowrap;overflow:hidden;text-overflow:ellipsis">'+e.name+'</div><div style="font-size:10px;color:#4a5a6a;margin-top:1px">'+metaStr+'</div></div>';
    // Timer si exercice en sec
    if(e.unit==='sec'&&e.duration>0){
      const timerRunning=timer&&timer.running;
      const timerLeft=timer?timer.left:e.duration*(e.bilateral?2:1);
      h+='<span class="recup-timer-display">'+formatTimerSec(timerLeft)+'</span>';
      h+='<button class="recup-timer-btn'+(timerRunning?' running':'')+'" onclick="toggleRecupTimer(\''+e.id+'\','+e.duration*(e.bilateral?2:1)+')">'+(timerRunning?'⏸':'▶')+'</button>';
    }
    h+='<button class="gym-icon-btn" onclick="showExInfo(\''+esc(e.name)+'\',\''+esc(e.info||'')+'\')">ℹ️</button>';
    h+='</div></div>';
  });
  if(pct===100){
    h+='<button class="recup-session-end-btn" onclick="endRecupSession()">✓ Terminer la séance</button>';
  } else {
    h+='<button class="recup-session-end-btn" style="opacity:0.6" onclick="endRecupSession()">✓ Terminer ('+pct+'% fait)</button>';
  }
  h+='</div>';return h;
}

// ══ RENDER POIDS ══
function renderPoids(){
  const weights=loadWeights(),today=todayKey();
  const todayW=weights[poidsDate]||'';
  const obj=loadObjective();
  const curW=weights[today]||(Object.values(weights).length?parseFloat(Object.values(weights).slice(-1)[0]):START_WEIGHT)||START_WEIGHT;
  const imc=(curW/(1.92*1.92)).toFixed(1);
  const diff=parseFloat((curW-START_WEIGHT).toFixed(1));
  const diffStr=(diff>=0?'+':'')+diff;
  const remaining=(obj.target-curW).toFixed(1);
  const daysSince=daysSinceStart();const weeksSince=daysSince/7;
  const rythme=weeksSince>0.5?(diff/weeksSince).toFixed(2):'—';
  const pts=[];const d=new Date();
  for(let i=13;i>=0;i--){const dd=new Date(d);dd.setDate(dd.getDate()-i);const k=dateToKey(dd);if(weights[k])pts.push({w:parseFloat(weights[k]),label:dd.getDate()+'/'+(dd.getMonth()+1),k});}
  let chartSvg='';
  if(pts.length>=2){
    const minW=Math.min(...pts.map(p=>p.w))-0.3;const maxW=Math.max(...pts.map(p=>p.w))+0.3;
    const PAD_L=10,PAD_R=10,PAD_TOP=26,PAD_BOT=20;const W=300,H=100;
    const chartW=W-PAD_L-PAD_R;const chartH=H;const yRange=maxW-minW||0.5;
    const toX=i=>PAD_L+i*(chartW/(pts.length-1));const toY=w=>PAD_TOP+chartH-((w-minW)/yRange)*chartH;
    const pathD=pts.map((p,i)=>(i===0?'M':'L')+toX(i).toFixed(1)+','+toY(p.w).toFixed(1)).join(' ');
    const fillD=pathD+' L'+toX(pts.length-1).toFixed(1)+','+(PAD_TOP+chartH)+' L'+toX(0).toFixed(1)+','+(PAD_TOP+chartH)+' Z';
    chartSvg='<svg viewBox="0 0 '+W+' '+(H+PAD_TOP+PAD_BOT)+'" xmlns="http://www.w3.org/2000/svg" style="width:100%;display:block">';
    chartSvg+='<defs><linearGradient id="wg" x1="0" y1="0" x2="0" y2="1"><stop offset="0%" stop-color="#4a8abf" stop-opacity="0.25"/><stop offset="100%" stop-color="#4a8abf" stop-opacity="0"/></linearGradient></defs>';
    chartSvg+='<path d="'+fillD+'" fill="url(#wg)"/><path d="'+pathD+'" fill="none" stroke="#4a8abf" stroke-width="2.5" stroke-linejoin="round" stroke-linecap="round"/>';
    pts.forEach((p,i)=>{const cx=toX(i).toFixed(1);const cy=toY(p.w).toFixed(1);const labelY=(i%2===0)?parseFloat(cy)-12:parseFloat(cy)+18;const isPoidsDate=p.k===poidsDate;chartSvg+='<circle cx="'+cx+'" cy="'+cy+'" r="'+(isPoidsDate?5:3.5)+'" fill="'+(isPoidsDate?'#e8c94a':'#4caf7d')+'"/><text x="'+cx+'" y="'+labelY+'" font-size="10" font-weight="700" fill="#d0d8e4" text-anchor="middle" font-family="Poppins,sans-serif">'+p.w+'</text>';});
    chartSvg+='<text x="'+PAD_L+'" y="'+(H+PAD_TOP+PAD_BOT-3)+'" font-size="9" fill="#4a5a6a" font-family="Poppins,sans-serif">'+pts[0].label+'</text>';
    chartSvg+='<text x="'+(W-PAD_R)+'" y="'+(H+PAD_TOP+PAD_BOT-3)+'" font-size="9" fill="#4a5a6a" text-anchor="end" font-family="Poppins,sans-serif">'+pts[pts.length-1].label+'</text>';
    chartSvg+='</svg>';
  }
  let ms='';MILESTONES.forEach(m=>{const diff2=(m.target-curW).toFixed(1),done=curW>=m.target;ms+='<div class="milestone"><span class="milestone-label">'+m.label+' — <b>'+m.target+'kg</b></span><span class="milestone-value" style="color:'+(done?'#4caf7d':'#e8c94a')+'">'+(done?'✓ Atteint':'+'+diff2+'kg')+'</span></div>';});
  const allSessions=getLastGymSessions(999);
  const recupSessions=loadRecupSessions();
  const recupLog=loadRecupLog();
  const allRecup=[...recupSessions,...recupLog].map(r=>({...r,_type:'recup'}));
  const allMixed=[...allSessions.map(s=>({...s,_type:'muscu'})),...allRecup].sort((a,b)=>new Date(b.date)-new Date(a.date));
  const displayedSessions=showAllSessions?allMixed:allMixed.slice(0,8);
  let gymHtml='';
  if(displayedSessions.length){displayedSessions.forEach(s=>{
    const sd=new Date(s.date);const dateStr=sd.getDate()+'/'+(sd.getMonth()+1);
    if(s._type==='muscu'){
      const g=MUSCLE_GROUPS.find(x=>x.id===s.gid);const name=g?g.name:s.gid==='_perso'?'Séance perso':s.gid==='_alea'?'Séance aléatoire':'Inconnu';const icon=g?g.icon:s.gid==='_perso'?'🎯':'🎲';
      gymHtml+='<div class="gym-session-row"><span class="gym-session-date">'+dateStr+'</span><span style="font-size:9px;background:#1a2535;color:#4a8abf;border-radius:4px;padding:1px 5px;font-weight:700;flex-shrink:0">Muscu</span><span class="gym-session-name">'+icon+' '+name+'</span><span class="gym-session-mood">'+(s.mood||'')+'</span></div>';
      if(s.note)gymHtml+='<div style="font-size:10px;color:#5a6a7a;padding:2px 0 4px 0;font-style:italic">'+s.note+'</div>';
    } else {
      const name=s.name||s.activityName||'Récup';
      gymHtml+='<div class="gym-session-row"><span class="gym-session-date">'+dateStr+'</span><span style="font-size:9px;background:#1a3a1a;color:#4caf7d;border-radius:4px;padding:1px 5px;font-weight:700;flex-shrink:0">Récup</span><span class="gym-session-name">'+name+'</span><span style="font-size:10px;color:#4a5a6a">'+(s.duration||'')+'</span></div>';
    }
  });if(allMixed.length>8)gymHtml+='<div style="text-align:center;margin-top:8px"><button onclick="showAllSessions=!showAllSessions;renderMain()" style="background:transparent;border:none;color:#4a6a8a;font-size:12px;cursor:pointer;font-family:Poppins,sans-serif;font-weight:600">'+(showAllSessions?'▲ Voir moins':'▼ Voir tout ('+allMixed.length+' séances)')+'</button></div>';}
  else gymHtml='<div style="font-size:11px;color:#3a4a5a;padding:8px 0">Aucune séance enregistrée</div>';
  const vol=getWeeklyVolume();let volStr='';if(vol.total>0){const parts=Object.entries(vol.groups).map(([k,v])=>k+(v>1?' ×'+v:''));volStr=vol.total+' séance'+(vol.total>1?'s':'')+' · '+parts.join(' · ');}else volStr='Aucune séance cette semaine';
  const streak=calcStreak(),avg7=calcAvg7();
  const startW2=weights[START_DATE]||START_WEIGHT;const todayWv=weights[today];
  const dTotal=todayWv?(parseFloat(todayWv)-parseFloat(startW2)).toFixed(1):'—';
  const d7=new Date();d7.setDate(d7.getDate()-7);const w7=weights[dateToKey(d7)];
  const dWeek=(todayWv&&w7)?(parseFloat(todayWv)-parseFloat(w7)).toFixed(1):'—';
  const isToday=poidsDate===today;
  return '<div class="content">'
    +'<div class="compact-cards">'
    +'<div class="compact-card"><div class="compact-card-label">Actuel</div><div class="compact-card-val" style="color:#4caf7d">'+curW+'kg</div><div class="compact-card-sub">'+diffStr+'kg depuis départ</div></div>'
    +'<div class="compact-card"><div class="compact-card-label">Objectif</div><div class="compact-card-val" style="color:#8ab0d0">'+obj.target+'kg</div><div class="compact-card-sub">'+remaining+'kg restants</div></div>'
    +'<div class="compact-card"><div class="compact-card-label">IMC</div><div class="compact-card-val" style="color:#e8c94a">'+imc+'</div><div class="compact-card-sub">J+'+daysSinceStart()+'</div></div>'
    +'<div class="compact-card"><div class="compact-card-label">Rythme</div><div class="compact-card-val" style="color:#bf9a4a;font-size:14px">'+(rythme!=='—'?(parseFloat(rythme)>=0?'+':'')+rythme+'kg':'—')+'</div><div class="compact-card-sub">par semaine</div></div>'
    +'</div>'
    +'<div style="display:flex;align-items:center;gap:8px;margin-bottom:6px">'
    +'<button class="date-btn" onclick="prevPoidsDay()">◀</button>'
    +'<span style="flex:1;font-size:11px;color:#4a6a8a;font-weight:600;text-align:center">'+formatDate(poidsDate)+'</span>'
    +'<button class="date-btn" onclick="nextPoidsDay()" '+(isToday?'disabled style="opacity:0.3;cursor:default"':'')+'>▶</button>'
    +'</div>'
    +'<div class="weight-panel">'
    +'<div class="weight-input-row"><input type="number" id="weight-input" placeholder="Ex: 70.2" step="0.1" min="40" max="200" value="'+todayW+'"><button class="weight-save-btn" onclick="saveWeightInputPoids()">💾 Sauvegarder</button></div>'
    +(pts.length>=2?'<div class="weight-chart"><div class="weight-chart-title">Courbe 14 jours <span style="color:#e8c94a;font-size:9px">● jour sélectionné</span></div>'+chartSvg+'</div>':'<div style="font-size:11px;color:#3a4a5a;padding:8px 0;text-align:center">Saisis au moins 2 poids pour voir la courbe</div>')
    +'<div style="margin-top:10px">'+ms+'</div>'
    +'<div style="margin-top:12px"><div class="section-title">Modifier l\'objectif</div><div style="display:flex;gap:8px;margin-top:6px"><input type="number" id="obj-input" placeholder="Ex: 82.5" step="0.5" min="50" max="200" value="'+obj.target+'" style="flex:1"><button onclick="saveObjectiveInput()" class="weight-save-btn">✓</button></div></div>'
    +'</div>'
    +'<div class="section-title" style="margin-top:14px">Historique des séances</div>'
    +'<div style="background:#141929;border:1px solid #1e2535;border-radius:10px;padding:8px 12px;margin-bottom:8px"><div style="font-size:11px;color:#6a7a8a;font-weight:600">Cette semaine</div><div style="font-size:12px;color:#8ab0d0;margin-top:3px;font-weight:500">'+volStr+'</div></div>'
    +'<div class="stats-panel">'+gymHtml+'</div>'
    +'<div class="section-title" style="margin-top:4px">Prise de masse</div>'
    +'<div class="stats-panel"><div class="stats-grid">'
    +'<div class="stat-box"><div class="stat-label">Delta total</div><div class="stat-value" style="color:'+(parseFloat(dTotal)>0?'#4caf7d':'#e8c94a')+'">'+(dTotal!=='—'?(parseFloat(dTotal)>=0?'+':'')+dTotal+'kg':'—')+'</div><div class="stat-sub">depuis 30/04</div></div>'
    +'<div class="stat-box"><div class="stat-label">Delta 7j</div><div class="stat-value" style="color:'+(parseFloat(dWeek)>0?'#4caf7d':'#e8c94a')+'">'+(dWeek!=='—'?(parseFloat(dWeek)>=0?'+':'')+dWeek+'kg':'—')+'</div><div class="stat-sub">cette semaine</div></div>'
    +'<div class="stat-box"><div class="stat-label">Streak P.</div><div class="stat-value" style="color:#4caf7d">'+streak+'</div><div class="stat-sub">jours protéines</div></div>'
    +'</div>'
    +'<div class="stats-grid" style="margin-top:8px">'
    +'<div class="stat-box"><div class="stat-label">Moy. 7j</div><div class="stat-value" style="color:'+(avg7>=PROT_TARGET()?'#4caf7d':'#e8c94a')+'">'+avg7+'g</div><div class="stat-sub">protéines/j</div></div>'
    +'<div class="stat-box"><div class="stat-label">Séances</div><div class="stat-value" style="color:#4a8abf">'+getTotalSessions()+'</div><div class="stat-sub">total muscu</div></div>'
    +'<div class="stat-box"><div class="stat-label">J+ proto.</div><div class="stat-value" style="color:#7a7ab0">'+daysSinceStart()+'</div><div class="stat-sub">depuis 30/04</div></div>'
    +'</div></div>'
    +'</div>';
}

// ══ RENDER DATA ══
function renderData(){
  const targets=loadTargets();
  return '<div class="content">'
    +'<div class="section-title">Objectifs nutritionnels</div>'
    +'<div class="backup-panel"><div style="margin-bottom:10px"><div style="font-size:11px;color:#e8c94a;font-weight:500;margin-bottom:6px">💪 Objectif protéines (g/jour)</div><div style="display:flex;gap:8px"><input type="number" id="tgt-prot" value="'+targets.prot+'" step="5" min="50" max="400" style="flex:1"><button onclick="saveTargetsInput()" class="weight-save-btn">✓</button></div></div>'
    +'<div style="margin-bottom:10px"><div style="font-size:11px;color:#4a8abf;font-weight:500;margin-bottom:6px">⚡ Objectif glucides (g/jour)</div><div style="display:flex;gap:8px"><input type="number" id="tgt-gluc" value="'+targets.gluc+'" step="10" min="50" max="600" style="flex:1"><button onclick="saveTargetsInput()" class="weight-save-btn">✓</button></div></div>'
    +'<div><div style="font-size:11px;color:#c4982a;font-weight:500;margin-bottom:6px">🌾 Objectif fibres (g/jour)</div><div style="display:flex;gap:8px"><input type="number" id="tgt-fiber" value="'+targets.fiber+'" step="2" min="10" max="100" style="flex:1"><button onclick="saveTargetsInput()" class="weight-save-btn">✓</button></div></div></div>'
    +'<div class="section-title" style="margin-top:14px">Sauvegarde & Restauration</div>'
    +'<div class="backup-panel"><p style="font-size:11px;color:#4a5a6a;margin-bottom:10px;line-height:1.5;font-weight:500">Copie tes données et colle-les dans <b style="color:#6a7a8a">Notes</b> sur iPhone.</p>'
    +'<button class="backup-btn backup-export" onclick="exportData()">📋 Copier mes données</button>'
    +'<textarea id="export-ta" style="display:none"></textarea>'
    +'<div style="font-size:11px;color:#4a5a6a;margin-bottom:6px;font-weight:500">Restaurer depuis une sauvegarde :</div>'
    +'<textarea id="import-ta" placeholder="Colle tes données ici..."></textarea>'
    +'<button class="backup-btn backup-import" onclick="importData()">📥 Restaurer</button></div>'
    +'<div class="section-title" style="margin-top:14px">Danger</div>'
    +'<div class="backup-panel"><button class="backup-btn" style="background:#1f1510;color:#e8943a;border-color:#3a2a1a;margin-bottom:8px" onclick="confirmReset()">🗑 Effacer les repas du jour</button>'
    +'<button class="backup-btn" style="background:#1f1010;color:#e85a4a;border-color:#3a1a1a" onclick="showModal(\'Effacer TOUTES les données ?\',()=>showModal(\'Dernière confirmation — irréversible\',()=>{try{for(let i=localStorage.length-1;i>=0;i--){const k=localStorage.key(i);if(k&&k.startsWith(\'vt_\'))localStorage.removeItem(k);}}catch(e){}renderAll();showToast(\'Données effacées.\');}))">🗑 Effacer toutes les données</button></div>'
    +'</div>';
}

function exportData(){const allKeys=new Set();try{for(let i=0;i<localStorage.length;i++){const k=localStorage.key(i);if(k&&k.startsWith('vt_'))allKeys.add(k);}}catch(e){}const keys=[];allKeys.forEach(k=>{const v=retrieve(k,null);if(v!==null)keys.push({key:k,value:JSON.stringify(v)});});if(!keys.length){alert('Aucune donnée.');return;}const txt=JSON.stringify(keys);const ta=document.getElementById('export-ta');ta.value=txt;ta.style.display='block';try{ta.select();ta.setSelectionRange(0,99999);document.execCommand('copy');showToast('Copié ! Colle dans Notes.');}catch(e){alert('Sélectionne tout le texte manuellement.');}}
function importData(){const txt=document.getElementById('import-ta')?.value.trim();if(!txt){alert('Colle tes données d\'abord.');return;}try{const items=JSON.parse(txt);items.forEach(it=>{const val=typeof it.value==='string'?JSON.parse(it.value):it.value;store(it.key,val);});document.getElementById('import-ta').value='';renderAll();showToast('Données restaurées !');}catch(e){alert('Format invalide.');}}
function formatDate(key){const[y,mo,d]=key.split('-');const date=new Date(y,mo-1,d);const days=['Dim','Lun','Mar','Mer','Jeu','Ven','Sam'];const months=['jan','fév','mar','avr','mai','jun','jul','aoû','sep','oct','nov','déc'];if(key===todayKey())return"Aujourd'hui — "+days[date.getDay()]+' '+d+' '+months[mo-1];return days[date.getDay()]+' '+d+' '+months[mo-1]+' '+y;}

// ══ MAIN RENDER ══
function renderMain(){
  const el=document.getElementById('main-content');
  if(currentView==='repas')el.innerHTML=renderRepas();
  else if(currentView==='muscu')el.innerHTML=renderMuscu();
  else if(currentView==='recup')el.innerHTML=renderRecup();
  else if(currentView==='poids')el.innerHTML=renderPoids();
  else el.innerHTML=renderData();
  if(currentView==='muscu'&&muscuSubView==='session'){document.body.classList.add('session-active');}
  else{document.body.classList.remove('session-active');}
}
function renderAll(){renderHeader();renderTabs();renderMain();}

document.addEventListener('visibilitychange',()=>{if(!document.hidden)renderAll();});
window.addEventListener('pageshow',()=>renderAll());
window.addEventListener('focus',()=>renderAll());

switchView('repas');
</script>
</body>
</html>
