[实习律师工作台 (10).html](https://github.com/user-attachments/files/28538130/10.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>律政工作台 - 实习律师学习与工作平台</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  :root {
    --morandi-pink: #C4A7A0;
    --morandi-green: #A8B5A0;
    --morandi-blue: #9AADBD;
    --morandi-beige: #D4C5B2;
    --morandi-purple: #B8A9C9;
    --morandi-warm-white: #F7F5F2;
    --morandi-gray: #9E9E9E;
    --morandi-dark: #5A5A6E;
    --morandi-text: #4A4A5A;
    --morandi-text-light: #8A8A9A;
    --card-bg: #FFFFFF;
    --sidebar-bg: #E8E4DF;
    --nav-bg: #C5CDD5;
    --urgent-color: #E88B8B;
    --shadow-sm: 0 1px 3px rgba(0,0,0,0.06);
    --shadow-md: 0 4px 12px rgba(0,0,0,0.08);
    --transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
  }
  body {
    font-family: -apple-system, "PingFang SC", "Noto Sans SC", "Microsoft YaHei", sans-serif;
    background: var(--morandi-warm-white);
    color: var(--morandi-text);
    display: flex;
    height: 100vh;
    width: 100vw;
    overflow: hidden;
    font-size: 14px;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }
  .sidebar {
    width: 260px;
    background: var(--sidebar-bg);
    padding: 20px 16px;
    display: flex;
    flex-direction: column;
    flex-shrink: 0;
    border-right: 1px solid rgba(0,0,0,0.06);
    overflow-y: auto;
  }
  .sidebar-logo {
    font-size: 20px;
    font-weight: 700;
    color: var(--morandi-dark);
    margin-bottom: 4px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .sidebar-logo .logo-icon {
    width: 36px; height: 36px;
    background: linear-gradient(135deg, var(--morandi-blue), var(--morandi-purple));
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    color: white; font-size: 18px; font-weight: bold;
    box-shadow: var(--shadow-sm);
  }
  .sidebar-subtitle {
    font-size: 12px;
    color: var(--morandi-text-light);
    margin-bottom: 28px;
    padding-left: 46px;
  }
  .sidebar-section { margin-bottom: 24px; }
  .sidebar-section-title {
    font-size: 11px;
    color: var(--morandi-gray);
    text-transform: uppercase;
    letter-spacing: 1.5px;
    margin-bottom: 10px;
    padding-left: 4px;
    font-weight: 600;
  }
  .nav-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 16px;
    border-radius: 10px;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    transition: var(--transition);
    margin-bottom: 4px;
    color: var(--morandi-text);
    position: relative;
    overflow: hidden;
  }
  .nav-item:hover { background: rgba(154,173,189,0.15); }
  .nav-item.active { background: rgba(154,173,189,0.25); color: var(--morandi-dark); }
  .nav-item .icon { font-size: 18px; width: 20px; text-align: center; opacity: 0.85; }
  .quick-case-item {
    padding: 10px 14px;
    border-radius: 8px;
    font-size: 13px;
    cursor: pointer;
    margin-bottom: 6px;
    border-left: 3px solid transparent;
    transition: var(--transition);
    background: rgba(255,255,255,0.4);
  }
  .quick-case-item:hover { background: rgba(255,255,255,0.7); transform: translateX(2px); }
  .quick-case-item.urgent { border-left-color: var(--urgent-color); }
  .quick-case-item.normal { border-left-color: var(--morandi-blue); }
  .quick-case-item.done { border-left-color: var(--morandi-green); }
  .quick-case-name { font-weight: 600; margin-bottom: 2px; }
  .quick-case-meta { font-size: 11px; color: var(--morandi-text-light); }
  .no-cases {
    padding: 16px;
    text-align: center;
    font-size: 12px;
    color: var(--morandi-text-light);
    background: rgba(255,255,255,0.3);
    border-radius: 8px;
  }
  .main { flex: 1; display: flex; flex-direction: column; overflow: hidden; width: 100%; min-width: 0; }
  .topnav {
    height: 64px;
    background: var(--card-bg);
    display: flex;
    align-items: center;
    padding: 0 28px;
    gap: 24px;
    flex-shrink: 0;
    box-shadow: 0 1px 3px rgba(0,0,0,0.04);
    border-bottom: 1px solid rgba(0,0,0,0.04);
  }
  .search-box { flex: 1; max-width: 420px; position: relative; }
  .search-box input {
    width: 100%;
    padding: 10px 20px 10px 44px;
    border: none;
    border-radius: 24px;
    background: var(--morandi-warm-white);
    font-size: 14px;
    outline: none;
    color: var(--morandi-text);
    transition: var(--transition);
  }
  .search-box input:focus { box-shadow: 0 0 0 2px rgba(154,173,189,0.3); background: white; }
  .search-box .search-icon { position: absolute; left: 16px; top: 50%; transform: translateY(-50%); color: var(--morandi-gray); font-size: 16px; }
  .topnav-right { display: flex; align-items: center; gap: 16px; margin-left: auto; }
  .notif-btn {
    width: 40px; height: 40px;
    border-radius: 50%;
    background: var(--morandi-warm-white);
    display: flex; align-items: center; justify-content: center;
    cursor: pointer; position: relative; font-size: 18px;
    transition: var(--transition);
  }
  .notif-btn:hover { background: var(--sidebar-bg); }
  .notif-btn .badge {
    position: absolute; top: 6px; right: 6px;
    width: 8px; height: 8px;
    background: var(--urgent-color);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }
  @keyframes pulse { 0%, 100% { transform: scale(1); opacity: 1; } 50% { transform: scale(1.2); opacity: 0.7; } }
  .user-avatar {
    width: 40px; height: 40px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--morandi-purple), var(--morandi-blue));
    display: flex; align-items: center; justify-content: center;
    color: white; font-size: 15px; font-weight: 600; cursor: pointer;
    box-shadow: var(--shadow-sm);
    transition: var(--transition);
  }
  .user-avatar:hover { transform: scale(1.05); }
  .content { flex: 1; padding: 24px 28px; overflow: auto; width: 100%; }
  .page { display: none; width: 100%; box-sizing: border-box; }
  .page.active { display: block; }
  .page-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 24px; flex-wrap: wrap; gap: 12px; }
  .page-title { font-size: 24px; font-weight: 700; color: var(--morandi-dark); }
  .btn {
    padding: 10px 20px;
    border: none;
    border-radius: 10px;
    font-size: 14px;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  .btn-primary {
    background: linear-gradient(135deg, var(--morandi-blue), var(--morandi-purple));
    color: white;
    box-shadow: 0 2px 8px rgba(154,173,189,0.3);
  }
  .btn-primary:hover { transform: translateY(-1px); box-shadow: 0 4px 12px rgba(154,173,189,0.4); }
  .btn-secondary { background: white; color: var(--morandi-text); border: 1px solid rgba(0,0,0,0.1); }
  .btn-secondary:hover { background: var(--morandi-warm-white); }
  .btn-danger { background: var(--urgent-color); color: white; }
  .btn-small { padding: 6px 12px; font-size: 12px; }
  .stat-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 16px; margin-bottom: 24px; width: 100%; }
  .stat-card {
    background: var(--card-bg);
    border-radius: 12px;
    padding: 16px;
    box-shadow: var(--shadow-sm);
    cursor: pointer;
    transition: var(--transition);
    border: 1px solid rgba(0,0,0,0.03);
    min-width: 140px;
  }
  .stat-card:hover { transform: translateY(-3px); box-shadow: var(--shadow-md); }
  .stat-card-icon {
    width: 36px; height: 36px;
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    margin-bottom: 10px;
  }
  .stat-card-icon.blue { background: rgba(154,173,189,0.2); }
  .stat-card-icon.green { background: rgba(168,181,160,0.2); }
  .stat-card-icon.purple { background: rgba(184,169,201,0.2); }
  .stat-card-icon.beige { background: rgba(212,197,178,0.3); }
  .stat-card-icon.pink { background: rgba(196,167,160,0.2); }
  .stat-card-value { font-size: 28px; font-weight: 700; margin-bottom: 4px; line-height: 1; }
  .stat-card-label { font-size: 12px; color: var(--morandi-text-light); font-weight: 500; }
  .two-col { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; margin-bottom: 24px; width: 100%; }
  .panel {
    background: var(--card-bg);
    border-radius: 12px;
    padding: 20px;
    box-shadow: var(--shadow-sm);
    border: 1px solid rgba(0,0,0,0.03);
    width: 100%;
    box-sizing: border-box;
    overflow: hidden;
  }
  .panel-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; }
  .panel-title { font-size: 16px; font-weight: 700; color: var(--morandi-dark); }
  .panel-more { font-size: 13px; color: var(--morandi-blue); cursor: pointer; font-weight: 500; }
  .panel-more:hover { text-decoration: underline; }
  .todo-item { display: flex; align-items: center; padding: 12px 0; border-bottom: 1px solid #F0EDE8; gap: 12px; }
  .todo-item:last-child { border-bottom: none; }
  .todo-dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; }
  .todo-dot.urgent { background: var(--urgent-color); }
  .todo-dot.important { background: var(--morandi-beige); }
  .todo-dot.normal { background: var(--morandi-blue); }
  .todo-content { flex: 1; }
  .todo-title { font-size: 14px; font-weight: 500; }
  .todo-meta { font-size: 12px; color: var(--morandi-text-light); margin-top: 2px; }
  .todo-time { font-size: 12px; color: var(--morandi-gray); }
  .chart-area { display: flex; align-items: center; gap: 28px; padding: 8px 0; }
  .chart-ring {
    width: 150px; height: 150px;
    border-radius: 50%;
    background: conic-gradient(
      var(--morandi-blue) 0% 25%,
      var(--morandi-green) 25% 42%,
      var(--morandi-beige) 42% 75%,
      var(--morandi-purple) 75% 92%,
      var(--morandi-gray) 92% 100%
    );
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    position: relative;
  }
  .chart-ring-inner {
    width: 100px; height: 100px;
    border-radius: 50%;
    background: var(--card-bg);
    display: flex; align-items: center; justify-content: center;
    flex-direction: column;
  }
  .chart-ring-value { font-size: 26px; font-weight: 700; }
  .chart-ring-label { font-size: 12px; color: var(--morandi-text-light); }
  .chart-legend { display: flex; flex-direction: column; gap: 10px; flex: 1; }
  .chart-legend-item {
    display: flex; align-items: center; justify-content: space-between;
    gap: 10px; font-size: 13px; padding: 6px 8px; border-radius: 6px;
    cursor: pointer; transition: var(--transition);
  }
  .chart-legend-item:hover { background: var(--morandi-warm-white); }
  .chart-legend-dot { width: 12px; height: 12px; border-radius: 4px; flex-shrink: 0; }
  .progress-bar-bg {
    width: 100%; height: 10px;
    background: var(--morandi-warm-white);
    border-radius: 5px;
    margin: 12px 0;
    overflow: hidden;
  }
  .progress-bar-fill {
    height: 100%; border-radius: 5px;
    background: linear-gradient(90deg, var(--morandi-green), var(--morandi-blue));
    transition: width 0.5s ease;
  }
  .study-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin-top: 20px; }
  .study-stat { text-align: center; padding: 16px 12px; background: var(--morandi-warm-white); border-radius: 10px; transition: var(--transition); }
  .study-stat:hover { transform: translateY(-2px); }
  .study-stat-value { font-size: 22px; font-weight: 700; color: var(--morandi-blue); }
  .study-stat-label { font-size: 12px; color: var(--morandi-text-light); margin-top: 4px; }
  .recommend-list { display: flex; flex-direction: column; gap: 10px; }
  .recommend-item {
    display: flex; align-items: center; gap: 12px;
    padding: 14px; background: var(--morandi-warm-white);
    border-radius: 10px; cursor: pointer; transition: var(--transition);
  }
  .recommend-item:hover { background: #E8E4DF; transform: translateX(4px); }
  .recommend-tag { padding: 4px 10px; border-radius: 6px; font-size: 11px; font-weight: 600; flex-shrink: 0; }
  .recommend-tag.law { background: rgba(154,173,189,0.2); color: var(--morandi-blue); }
  .recommend-tag.case { background: rgba(184,169,201,0.2); color: var(--morandi-purple); }
  .recommend-tag.template { background: rgba(168,181,160,0.2); color: var(--morandi-green); }
  .recommend-text { font-size: 14px; flex: 1; font-weight: 500; }
  .recommend-arrow { color: var(--morandi-gray); font-size: 16px; }
  .board-toolbar { display: flex; align-items: center; gap: 16px; margin-bottom: 20px; flex-wrap: wrap; }
  .board-filter {
    padding: 8px 14px; border: 1px solid #E0DCD6;
    border-radius: 8px; font-size: 13px; background: white;
    color: var(--morandi-text); cursor: pointer; outline: none;
  }
  .board-view-toggle { display: flex; background: var(--morandi-warm-white); border-radius: 8px; overflow: hidden; }
  .board-view-btn {
    padding: 8px 16px; font-size: 13px; cursor: pointer;
    border: none; background: transparent; color: var(--morandi-text-light);
    font-weight: 500; transition: var(--transition);
  }
  .board-view-btn.active { background: var(--morandi-blue); color: white; }
  .board-legend {
    display: flex; gap: 24px; margin-bottom: 20px;
    padding: 12px 16px; background: white; border-radius: 10px;
    font-size: 13px; color: var(--morandi-text-light); box-shadow: var(--shadow-sm);
  }
  .board-legend-item { display: flex; align-items: center; gap: 8px; }
  .board-legend-dot { width: 12px; height: 12px; border-radius: 4px; }
  .board-legend-dot.urgent { background: var(--urgent-color); }
  .board-legend-dot.important { background: var(--morandi-beige); }
  .board-legend-dot.normal { background: var(--morandi-blue); }
  .board-columns { display: grid; grid-template-columns: repeat(5, minmax(0, 1fr)); gap: 14px; min-height: 550px; width: 100%; }
  .board-column {
    background: rgba(255,255,255,0.6);
    border-radius: 12px;
    padding: 14px;
    min-height: 200px;
    width: 100%;
    box-sizing: border-box;
    overflow: hidden;
  }
  .board-column-header {
    display: flex; align-items: center; justify-content: space-between;
    margin-bottom: 14px; padding: 0 2px;
  }
  .board-column-title { font-size: 14px; font-weight: 700; display: flex; align-items: center; gap: 8px; color: var(--morandi-dark); }
  .board-column-count { font-size: 12px; padding: 2px 10px; border-radius: 12px; color: white; font-weight: 600; }
  .board-column-count.blue { background: var(--morandi-blue); }
  .board-column-count.green { background: var(--morandi-green); }
  .board-column-count.beige { background: #A89070; color: white; }
  .board-column-count.pink { background: var(--morandi-pink); }
  .board-column-count.gray { background: var(--morandi-gray); }
  .board-card {
    background: white;
    border-radius: 10px;
    padding: 14px;
    margin-bottom: 10px;
    cursor: grab;
    transition: var(--transition);
    border-left: 3px solid transparent;
    box-shadow: var(--shadow-sm);
    border: 1px solid rgba(0,0,0,0.04);
    width: 100%;
    box-sizing: border-box;
    overflow: hidden;
  }
  .board-card:hover { box-shadow: var(--shadow-md); transform: translateY(-2px); }
  .board-card.dragging { opacity: 0.5; transform: rotate(2deg); }
  .board-card.urgent { border-left-color: var(--urgent-color); }
  .board-card.important { border-left-color: var(--morandi-beige); }
  .board-card.normal { border-left-color: var(--morandi-blue); }
  .board-card-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
  .board-card-urgency { font-size: 10px; padding: 3px 8px; border-radius: 4px; font-weight: 600; text-transform: uppercase; }
  .board-card-urgency.urgent { background: rgba(232,139,139,0.2); color: #A85A5A; }
  .board-card-urgency.important { background: rgba(212,197,178,0.4); color: #887050; }
  .board-card-urgency.normal { background: rgba(154,173,189,0.2); color: #5A7A8A; }
  .board-card-deadline { font-size: 11px; color: var(--morandi-gray); font-weight: 500; }
  .board-card-deadline.soon { color: var(--urgent-color); }
  .board-card-case-no { font-size: 11px; color: var(--morandi-text-light); margin-bottom: 4px; }
  .board-card-name { font-size: 14px; font-weight: 700; margin-bottom: 4px; color: var(--morandi-dark); }
  .board-card-party { font-size: 12px; color: var(--morandi-text-light); margin-bottom: 12px; }
  .board-card-actions { display: flex; gap: 6px; flex-wrap: wrap; }
  .board-footer {
    display: flex; justify-content: center; gap: 40px;
    margin-top: 20px; padding: 20px; background: white;
    border-radius: 12px; box-shadow: var(--shadow-sm);
  }
  .board-stat { text-align: center; }
  .board-stat-value { font-size: 24px; font-weight: 700; }
  .board-stat-label { font-size: 13px; color: var(--morandi-text-light); margin-top: 4px; }
  .modal-overlay {
    position: fixed; top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(0,0,0,0.4); display: flex; align-items: center; justify-content: center;
    z-index: 1000; opacity: 0; visibility: hidden; transition: var(--transition);
    backdrop-filter: blur(4px);
  }
  .modal-overlay.show { opacity: 1; visibility: visible; }
  .modal {
    background: white; border-radius: 16px; width: 90%; max-width: 600px;
    max-height: 90vh; overflow-y: auto; box-shadow: 0 20px 60px rgba(0,0,0,0.15);
    transform: translateY(20px) scale(0.95); transition: var(--transition);
  }
  .modal-overlay.show .modal { transform: translateY(0) scale(1); }
  .modal-large { max-width: 800px; }
  .modal-header { padding: 20px 24px; border-bottom: 1px solid #F0EDE8; display: flex; justify-content: space-between; align-items: center; }
  .modal-title { font-size: 18px; font-weight: 700; color: var(--morandi-dark); }
  .modal-close {
    width: 32px; height: 32px; border-radius: 50%; background: var(--morandi-warm-white);
    border: none; cursor: pointer; font-size: 18px; display: flex; align-items: center; justify-content: center;
    transition: var(--transition);
  }
  .modal-close:hover { background: var(--sidebar-bg); }
  .modal-body { padding: 24px; }
  .form-group { margin-bottom: 18px; }
  .form-label { display: block; font-size: 13px; font-weight: 600; margin-bottom: 8px; color: var(--morandi-dark); }
  .form-label .required { color: var(--urgent-color); margin-left: 2px; }
  .form-input, .form-select, .form-textarea {
    width: 100%; padding: 10px 14px; border: 1px solid #E0DCD6;
    border-radius: 8px; font-size: 14px; outline: none;
    transition: var(--transition); background: white; color: var(--morandi-text);
    font-family: inherit;
  }
  .form-input:focus, .form-select:focus, .form-textarea:focus {
    border-color: var(--morandi-blue); box-shadow: 0 0 0 3px rgba(154,173,189,0.15);
  }
  .form-textarea { resize: vertical; min-height: 120px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  .modal-footer { padding: 16px 24px; border-top: 1px solid #F0EDE8; display: flex; justify-content: flex-end; gap: 12px; }
  .detail-section { margin-bottom: 24px; }
  .detail-section-title {
    font-size: 15px; font-weight: 700; margin-bottom: 12px; color: var(--morandi-dark);
    padding-bottom: 8px; border-bottom: 2px solid var(--morandi-warm-white);
  }
  .detail-row { display: flex; padding: 10px 0; border-bottom: 1px solid #F8F6F2; }
  .detail-row:last-child { border-bottom: none; }
  .detail-label { width: 100px; font-size: 13px; color: var(--morandi-text-light); flex-shrink: 0; }
  .detail-value { flex: 1; font-size: 14px; font-weight: 500; }
  .timeline { position: relative; padding-left: 24px; }
  .timeline::before { content: ''; position: absolute; left: 5px; top: 8px; bottom: 8px; width: 2px; background: #E0DCD6; }
  .timeline-item { position: relative; padding-bottom: 16px; }
  .timeline-item::before {
    content: ''; position: absolute; left: -21px; top: 4px;
    width: 10px; height: 10px; border-radius: 50%;
    background: var(--morandi-blue); border: 2px solid white;
    box-shadow: 0 0 0 2px var(--morandi-blue);
  }
  .timeline-date { font-size: 11px; color: var(--morandi-gray); margin-bottom: 2px; }
  .timeline-content { font-size: 13px; }
  .empty-state { text-align: center; padding: 40px 20px; color: var(--morandi-text-light); }
  .empty-state-icon { font-size: 48px; margin-bottom: 12px; opacity: 0.5; }
  .empty-state-text { font-size: 15px; margin-bottom: 8px; }
  .empty-state-hint { font-size: 12px; }

  .plan-card { background: white; border-radius: 12px; padding: 20px; box-shadow: var(--shadow-sm); margin-bottom: 16px; }
  .plan-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; }
  .plan-title { font-size: 16px; font-weight: 700; color: var(--morandi-dark); }
  .plan-progress { display: flex; align-items: center; gap: 10px; }
  .plan-progress-bar { width: 120px; height: 8px; background: var(--morandi-warm-white); border-radius: 4px; overflow: hidden; }
  .plan-progress-fill { height: 100%; background: linear-gradient(90deg, var(--morandi-green), var(--morandi-blue)); }
  .plan-progress-text { font-size: 13px; font-weight: 700; color: var(--morandi-blue); }
  .plan-tasks { margin-top: 16px; }
  .plan-task { display: flex; align-items: center; gap: 12px; padding: 10px 0; border-bottom: 1px solid #F8F6F2; cursor: pointer; }
  .plan-task:last-child { border-bottom: none; }
  .task-checkbox {
    width: 20px; height: 20px; border-radius: 6px;
    border: 2px solid var(--morandi-blue); cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: var(--transition); flex-shrink: 0; color: transparent;
  }
  .task-checkbox.completed { background: var(--morandi-green); border-color: var(--morandi-green); color: white; }
  .task-content { flex: 1; }
  .task-title { font-size: 14px; font-weight: 500; }
  .task-title.completed { text-decoration: line-through; color: var(--morandi-gray); }
  .task-date { font-size: 12px; color: var(--morandi-text-light); margin-top: 2px; }
  .toast-container { position: fixed; top: 20px; right: 20px; z-index: 2000; }
  .toast {
    background: white; padding: 14px 20px; border-radius: 10px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.12); margin-bottom: 10px;
    display: flex; align-items: center; gap: 10px;
    animation: slideIn 0.3s ease; font-size: 14px; font-weight: 500;
  }
  @keyframes slideIn { from { transform: translateX(100%); opacity: 0; } to { transform: translateX(0); opacity: 1; } }
  .toast.success { border-left: 4px solid var(--morandi-green); }
  .toast.error { border-left: 4px solid var(--urgent-color); }
  .toast.info { border-left: 4px solid var(--morandi-blue); }
  ::-webkit-scrollbar { width: 8px; height: 8px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: #D0CCC4; border-radius: 4px; }
  ::-webkit-scrollbar-thumb:hover { background: #B0ACA4; }

  /* 日历样式 */
  .calendar-nav { display: flex; align-items: center; justify-content: space-between; margin-bottom: 20px; }
  .calendar-nav button {
    background: white; border: 1px solid #E0DCD6; padding: 8px 16px;
    border-radius: 8px; cursor: pointer; font-size: 14px; transition: var(--transition);
  }
  .calendar-nav button:hover { background: var(--morandi-warm-white); }
  .calendar-nav h2 { font-size: 20px; font-weight: 700; color: var(--morandi-dark); }
  .calendar-grid { display: grid; grid-template-columns: repeat(7, minmax(0, 1fr)); gap: 8px; width: 100%; }
  .calendar-weekday {
    text-align: center; padding: 12px; font-size: 13px; font-weight: 600;
    color: var(--morandi-text-light); background: transparent;
  }
  .calendar-day {
    background: white; border-radius: 10px; padding: 12px; min-height: 100px;
    cursor: pointer; transition: var(--transition); border: 2px solid transparent;
    box-shadow: var(--shadow-sm);
  }
  .calendar-day:hover { transform: translateY(-2px); box-shadow: var(--shadow-md); }
  .calendar-day.today { border-color: var(--morandi-blue); background: rgba(154,173,189,0.05); }
  .calendar-day.other-month { opacity: 0.4; }
  .calendar-day-number { font-size: 16px; font-weight: 700; margin-bottom: 8px; color: var(--morandi-dark); }
  .calendar-event {
    font-size: 11px; padding: 4px 8px; border-radius: 4px; margin-bottom: 4px;
    white-space: nowrap; overflow: hidden; text-overflow: ellipsis;
    background: rgba(154,173,189,0.15); color: var(--morandi-blue);
  }
  .calendar-event.urgent { background: rgba(232,139,139,0.2); color: #A85A5A; }
  .calendar-event.case { background: rgba(184,169,201,0.2); color: var(--morandi-purple); }
  .calendar-event.log { background: rgba(168,181,160,0.2); color: var(--morandi-green); }
  .calendar-event-more { font-size: 11px; color: var(--morandi-text-light); text-align: center; }

  /* 实习日志样式 */
  .journal-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; }
  .journal-stats { display: flex; gap: 24px; }
  .journal-stat { text-align: center; }
  .journal-stat-value { font-size: 28px; font-weight: 700; color: var(--morandi-blue); }
  .journal-stat-label { font-size: 12px; color: var(--morandi-text-light); }
  .journal-list { display: flex; flex-direction: column; gap: 12px; }
  .journal-item {
    background: white; border-radius: 12px; padding: 20px;
    box-shadow: var(--shadow-sm); transition: var(--transition);
  }
  .journal-item:hover { box-shadow: var(--shadow-md); }
  .journal-item-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; }
  .journal-item-date { font-size: 16px; font-weight: 700; color: var(--morandi-dark); }
  .journal-item-actions { display: flex; gap: 8px; }
  .journal-item-content { font-size: 14px; line-height: 1.8; color: var(--morandi-text); }
  .journal-item-tags { display: flex; gap: 8px; margin-top: 12px; flex-wrap: wrap; }
  .journal-item-tag { font-size: 11px; padding: 3px 10px; background: var(--morandi-warm-white); border-radius: 4px; color: var(--morandi-text-light); }
  .tabs { display: flex; gap: 8px; margin-bottom: 20px; border-bottom: 2px solid #E8E4DF; padding-bottom: 12px; }
  .tab { padding: 8px 20px; border-radius: 8px; cursor: pointer; font-size: 14px; font-weight: 600; color: var(--morandi-text-light); transition: var(--transition); }
  .tab.active { background: var(--morandi-blue); color: white; }
  .tab:hover:not(.active) { background: var(--morandi-warm-white); }
  .template-categories { display: flex; flex-direction: column; gap: 16px; }
  .template-category {
    background: white; border-radius: 12px; padding: 20px;
    box-shadow: var(--shadow-sm); cursor: pointer; transition: var(--transition);
  }
  .template-category:hover { transform: translateY(-2px); box-shadow: var(--shadow-md); }
  .template-category-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; }
  .template-category-title { font-size: 16px; font-weight: 700; color: var(--morandi-dark); display: flex; align-items: center; gap: 10px; }
  .template-category-count { font-size: 13px; color: var(--morandi-blue); font-weight: 600; }
  .template-category-desc { font-size: 13px; color: var(--morandi-text-light); }
  .template-item {
    background: var(--morandi-warm-white); border-radius: 8px; padding: 12px 16px;
    margin-bottom: 8px; display: flex; justify-content: space-between; align-items: center;
    cursor: pointer; transition: var(--transition);
  }
  .template-item:hover { background: #E8E4DF; }
  .template-item-title { font-size: 14px; font-weight: 500; }
  .template-item-actions { display: flex; gap: 6px; }
  .hidden { display: none !important; }
  .loading { text-align: center; padding: 40px; color: var(--morandi-text-light); }
  .markdown-content h3 { font-size: 16px; margin: 16px 0 8px; color: var(--morandi-dark); }
  .markdown-content p { margin-bottom: 12px; line-height: 1.8; }
  .markdown-content ul, .markdown-content ol { margin-left: 20px; margin-bottom: 12px; }
  .markdown-content li { margin-bottom: 4px; }
  .markdown-content strong { color: var(--morandi-dark); }
  .back-btn { display: flex; align-items: center; gap: 8px; cursor: pointer; font-size: 14px; color: var(--morandi-blue); margin-bottom: 16px; font-weight: 600; }
  .back-btn:hover { text-decoration: underline; }
</style>
</head>
<body>
  <div class="sidebar">
    <div class="sidebar-logo">
      <div class="logo-icon">⚖️</div>
      律政工作台
    </div>
    <div class="sidebar-subtitle">实习律师专属平台</div>
    <div class="sidebar-section">
      <div class="sidebar-section-title">导航</div>
      <div class="nav-item active" onclick="navigate('home')">
        <span class="icon">🏠</span> 首页工作台
      </div>
      <div class="nav-item" onclick="navigate('board')">
        <span class="icon">📋</span> 案件管理看板
      </div>

      <div class="nav-item" onclick="navigate('templates')">
        <span class="icon">📝</span> 文书模板库
      </div>
      <div class="nav-item" onclick="navigate('journal')">
        <span class="icon">📓</span> 实习日志
      </div>
      <div class="nav-item" onclick="navigate('calendar')">
        <span class="icon">📅</span> 日程日历
      </div>
    </div>
    <div class="sidebar-section">
      <div class="sidebar-section-title">最近案件</div>
      <div id="sidebarCases"></div>
    </div>
  </div>
  <div class="main">
    <div class="topnav">
      <div class="search-box">
        <span class="search-icon">🔍</span>
        <input type="text" placeholder="搜索案件、法条、文书... (Ctrl+K)" id="globalSearch">
      </div>
      <div class="topnav-right">
        <div class="notif-btn">🔔<div class="badge"></div></div>
        <div class="user-avatar">喵</div>
      </div>
    </div>

    <!-- 首页 -->
    <div class="content page active" id="page-home">
      <div class="page-header">
        <div class="page-title">👋 你好，喵律师，今天过得怎么样？</div>
        <button class="btn btn-primary" onclick="openCaseModal()">➕ 新建案件</button>
      </div>
      <div class="stat-grid">
        <div class="stat-card">
          <div class="stat-card-icon blue">📋</div>
          <div class="stat-card-value" id="statTotal">0</div>
          <div class="stat-card-label">案件总数</div>
        </div>
        <div class="stat-card">
          <div class="stat-card-icon pink">⚠️</div>
          <div class="stat-card-value" id="statUrgent">0</div>
          <div class="stat-card-label">临期案件</div>
        </div>
        <div class="stat-card">
          <div class="stat-card-icon beige">📝</div>
          <div class="stat-card-value" id="statDocs">0</div>
          <div class="stat-card-label">在办案件</div>
        </div>
        <div class="stat-card">
          <div class="stat-card-icon green">📓</div>
          <div class="stat-card-value" id="journalCount">0</div>
          <div class="stat-card-label">实习日志</div>
        </div>
        <div class="stat-card">
          <div class="stat-card-icon purple">📑</div>
          <div class="stat-card-value" id="templateCount">0</div>
          <div class="stat-card-label">文书模板</div>
        </div>
      </div>
      <div class="two-col">
        <div class="panel">
          <div class="panel-header">
            <div class="panel-title">📋 案件状态分布</div>
          </div>
          <div class="chart-area">
            <div class="chart-ring">
              <div class="chart-ring-inner">
                <div class="chart-ring-value" id="chartTotal">0</div>
                <div class="chart-ring-label">件案件</div>
              </div>
            </div>
            <div class="chart-legend" id="chartLegend"></div>
          </div>
        </div>
        <div class="panel">
          <div class="panel-header">
            <div class="panel-title">✅ 今日待办</div>
            <div class="panel-more" onclick="navigate('calendar')">查看全部 →</div>
          </div>
          <div id="homeTodos"></div>
        </div>
      </div>
      <div class="panel" style="max-width: 600px;">
        <div class="panel-header">
          <div class="panel-title">📅 本周日程</div>
          <div class="panel-more" onclick="navigate('calendar')">查看日历 →</div>
        </div>
        <div id="weekSchedule">
          <div class="todo-item">
            <div class="todo-dot urgent"></div>
            <div class="todo-content">
              <div class="todo-title">提交第5周实习日志</div>
              <div class="todo-meta">本周五 24:00前</div>
            </div>
          </div>
          <div class="todo-item">
            <div class="todo-dot normal"></div>
            <div class="todo-content">
              <div class="todo-title">张某案证据交换</div>
              <div class="todo-meta">周三 10:00</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- 案件管理看板 -->
    <div class="content page" id="page-board">
      <div class="page-header">
        <div class="page-title">📋 案件管理看板</div>
        <button class="btn btn-primary" onclick="openCaseModal()">➕ 新建案件</button>
      </div>
      <div class="board-toolbar">
        <select class="board-filter" id="filterType" onchange="filterCases()">
          <option value="">全部类型</option>
          <option value="买卖合同纠纷">买卖合同纠纷</option>
          <option value="民间借贷纠纷">民间借贷纠纷</option>
          <option value="离婚纠纷">离婚纠纷</option>
          <option value="侵权责任纠纷">侵权责任纠纷</option>
          <option value="劳动争议">劳动争议</option>
        </select>
        <select class="board-filter" id="filterUrgency" onchange="filterCases()">
          <option value="">全部紧急程度</option>
          <option value="urgent">紧急</option>
          <option value="important">重要</option>
          <option value="normal">正常</option>
        </select>
      </div>
      <div class="board-legend">
        <div class="board-legend-item"><div class="board-legend-dot urgent"></div> 紧急</div>
        <div class="board-legend-item"><div class="board-legend-dot important"></div> 重要</div>
        <div class="board-legend-item"><div class="board-legend-dot normal"></div> 正常</div>
      </div>
      <div class="board-columns">
        <div class="board-column" data-status="filing">
          <div class="board-column-header">
            <div class="board-column-title">📥 立案中</div>
            <div class="board-column-count blue" id="count-filing">0</div>
          </div>
          <div id="col-filing"></div>
        </div>
        <div class="board-column" data-status="preparation">
          <div class="board-column-header">
            <div class="board-column-title">📝 准备中</div>
            <div class="board-column-count green" id="count-preparation">0</div>
          </div>
          <div id="col-preparation"></div>
        </div>
        <div class="board-column" data-status="trial">
          <div class="board-column-header">
            <div class="board-column-title">⚖️ 审理中</div>
            <div class="board-column-count beige" id="count-trial">0</div>
          </div>
          <div id="col-trial"></div>
        </div>
        <div class="board-column" data-status="closing">
          <div class="board-column-header">
            <div class="board-column-title">🎯 结案中</div>
            <div class="board-column-count pink" id="count-closing">0</div>
          </div>
          <div id="col-closing"></div>
        </div>
        <div class="board-column" data-status="archived">
          <div class="board-column-header">
            <div class="board-column-title">📦 已归档</div>
            <div class="board-column-count gray" id="count-archived">0</div>
          </div>
          <div id="col-archived"></div>
        </div>
      </div>
      <div class="board-footer">
        <div class="board-stat"><div class="board-stat-value" id="foot-filing">0</div><div class="board-stat-label">立案中</div></div>
        <div class="board-stat"><div class="board-stat-value" id="foot-preparation">0</div><div class="board-stat-label">准备中</div></div>
        <div class="board-stat"><div class="board-stat-value" id="foot-trial">0</div><div class="board-stat-label">审理中</div></div>
        <div class="board-stat"><div class="board-stat-value" id="foot-closing">0</div><div class="board-stat-label">结案中</div></div>
        <div class="board-stat"><div class="board-stat-value" id="foot-archived">0</div><div class="board-stat-label">已归档</div></div>
      </div>
    </div>



    <!-- 文书模板库 -->
    <div class="content page" id="page-templates">
      <div class="page-header">
        <div class="page-title" id="templatePageTitle">📝 文书模板库</div>
        <div>
          <button class="btn btn-secondary" onclick="openCategoryModal()">📁 新建分类</button>
          <button class="btn btn-primary" onclick="openTemplateModal()">➕ 新建模板</button>
        </div>
      </div>
      <div id="templateCategoriesContainer">
        <div class="template-categories" id="templateCategories"></div>
      </div>
      <div id="templateListContainer" class="hidden">
        <div class="back-btn" onclick="backToTemplateCategories()">← 返回分类</div>
        <div id="templateList"></div>
      </div>
    </div>

    <!-- 实习日志 -->
    <div class="content page" id="page-journal">
      <div class="page-header">
        <div class="page-title">📓 实习日志</div>
        <button class="btn btn-primary" onclick="openJournalModal()">✍️ 写日记</button>
      </div>
      <div class="panel" style="margin-bottom: 24px;">
        <div class="journal-header">
          <div class="journal-stats">
            <div class="journal-stat">
              <div class="journal-stat-value" id="journalTotal">0</div>
              <div class="journal-stat-label">总日志数</div>
            </div>
            <div class="journal-stat">
              <div class="journal-stat-value" id="journalTarget">--</div>
              <div class="journal-stat-label">目标数量</div>
            </div>
            <div class="journal-stat">
              <div class="journal-stat-value" id="journalProgress">0%</div>
              <div class="journal-stat-label">完成进度</div>
            </div>
          </div>
          <button class="btn btn-secondary" onclick="openJournalSettings()">⚙️ 设置目标</button>
        </div>
        <div class="progress-bar-bg">
          <div class="progress-bar-fill" id="journalProgressBar" style="width: 0%"></div>
        </div>
      </div>
      <div class="journal-list" id="journalList"></div>
    </div>

    <!-- 日程日历 -->
    <div class="content page" id="page-calendar">
      <div class="page-header">
        <div class="page-title">📅 日程日历</div>
        <button class="btn btn-primary" onclick="openEventModal()">➕ 新建日程</button>
      </div>
      <div class="panel">
        <div class="calendar-nav">
          <button onclick="prevMonth()">← 上月</button>
          <h2 id="calendarTitle">2025年1月</h2>
          <button onclick="nextMonth()">下月 →</button>
        </div>
        <div class="calendar-grid">
          <div class="calendar-weekday">周日</div>
          <div class="calendar-weekday">周一</div>
          <div class="calendar-weekday">周二</div>
          <div class="calendar-weekday">周三</div>
          <div class="calendar-weekday">周四</div>
          <div class="calendar-weekday">周五</div>
          <div class="calendar-weekday">周六</div>
        </div>
        <div class="calendar-grid" id="calendarDays"></div>
      </div>
    </div>
  </div>

  <!-- 新建案件模态框 -->
  <div class="modal-overlay" id="caseModal">
    <div class="modal">
      <div class="modal-header">
        <div class="modal-title">➕ 新建案件</div>
        <button class="modal-close" onclick="closeCaseModal()">×</button>
      </div>
      <div class="modal-body">
        <form id="caseForm" onsubmit="saveCase(event)">
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">案号 <span class="required">*</span></label>
              <input type="text" class="form-input" name="caseNo" placeholder="如：(2025)京0105民初1234号" required>
            </div>
            <div class="form-group">
              <label class="form-label">案件类型 <span class="required">*</span></label>
              <select class="form-select" name="caseType" required>
                <option value="">请选择</option>
                <option value="买卖合同纠纷">买卖合同纠纷</option>
                <option value="民间借贷纠纷">民间借贷纠纷</option>
                <option value="离婚纠纷">离婚纠纷</option>
                <option value="侵权责任纠纷">侵权责任纠纷</option>
                <option value="劳动争议">劳动争议</option>
              </select>
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">案件名称 <span class="required">*</span></label>
            <input type="text" class="form-input" name="caseName" placeholder="如：张某与某公司买卖合同纠纷" required>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">原告</label>
              <input type="text" class="form-input" name="plaintiff" placeholder="原告姓名/名称">
            </div>
            <div class="form-group">
              <label class="form-label">被告</label>
              <input type="text" class="form-input" name="defendant" placeholder="被告姓名/名称">
            </div>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">受理法院</label>
              <input type="text" class="form-input" name="court" placeholder="如：北京市朝阳区人民法院">
            </div>
            <div class="form-group">
              <label class="form-label">截止日期 <span class="required">*</span></label>
              <input type="date" class="form-input" name="deadline" required>
            </div>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">紧急程度</label>
              <select class="form-select" name="urgency">
                <option value="normal">正常</option>
                <option value="important">重要</option>
                <option value="urgent">紧急</option>
              </select>
            </div>
            <div class="form-group">
              <label class="form-label">案件状态</label>
              <select class="form-select" name="status">
                <option value="filing">立案中</option>
                <option value="preparation">准备中</option>
                <option value="trial">审理中</option>
                <option value="closing">结案中</option>
                <option value="archived">已归档</option>
              </select>
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">案情摘要</label>
            <textarea class="form-textarea" name="summary" rows="3" placeholder="简要描述案件事实和当前进展"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" onclick="closeCaseModal()">取消</button>
        <button type="submit" form="caseForm" class="btn btn-primary">保存案件</button>
      </div>
    </div>
  </div>

  <!-- 案件详情模态框 -->
  <div class="modal-overlay" id="detailModal">
    <div class="modal modal-large">
      <div class="modal-header">
        <div class="modal-title">📋 案件详情</div>
        <button class="modal-close" onclick="closeDetailModal()">×</button>
      </div>
      <div class="modal-body" id="detailContent"></div>
      <div class="modal-footer">
        <button type="button" class="btn btn-danger" onclick="deleteCurrentCase()">删除案件</button>
        <button type="button" class="btn btn-secondary" onclick="closeDetailModal()">关闭</button>
      </div>
    </div>
  </div>

  <!-- 新建日志模态框 -->
  <div class="modal-overlay" id="journalModal">
    <div class="modal modal-large">
      <div class="modal-header">
        <div class="modal-title">✍️ 实习日志</div>
        <button class="modal-close" onclick="closeJournalModal()">×</button>
      </div>
      <div class="modal-body">
        <form id="journalForm" onsubmit="saveJournal(event)">
          <input type="hidden" name="journalId" id="journalId">
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">日期 <span class="required">*</span></label>
              <input type="date" class="form-input" name="journalDate" id="journalDate" required>
            </div>
            <div class="form-group">
              <label class="form-label">周记编号</label>
              <input type="text" class="form-input" name="journalWeek" placeholder="如：第5周">
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">实习内容 <span class="required">*</span></label>
            <textarea class="form-textarea" name="journalContent" id="journalContent" rows="8" placeholder="详细记录今天的实习内容、学到的知识、遇到的问题等..." required></textarea>
          </div>
          <div class="form-group">
            <label class="form-label">标签</label>
            <input type="text" class="form-input" name="journalTags" placeholder="用逗号分隔，如：立案,合同,法律咨询">
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" onclick="closeJournalModal()">取消</button>
        <button type="submit" form="journalForm" class="btn btn-primary">保存日志</button>
      </div>
    </div>
  </div>

  <!-- 日志设置模态框 -->
  <div class="modal-overlay" id="journalSettingsModal">
    <div class="modal">
      <div class="modal-header">
        <div class="modal-title">⚙️ 日志目标设置</div>
        <button class="modal-close" onclick="closeJournalSettingsModal()">×</button>
      </div>
      <div class="modal-body">
        <form id="journalSettingsForm" onsubmit="saveJournalSettings(event)">
          <div class="form-group">
            <label class="form-label">目标日志数量 <span class="required">*</span></label>
            <input type="number" class="form-input" name="journalTarget" id="journalTargetInput" placeholder="请输入律协要求的日志总数" min="1" required>
          </div>
          <div class="form-group">
            <label class="form-label">说明</label>
            <p style="font-size: 13px; color: var(--morandi-text-light); line-height: 1.6;">
              设置目标数量后，系统会自动计算完成进度。不同地区律协要求不同，请根据实际要求填写。
            </p>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" onclick="closeJournalSettingsModal()">取消</button>
        <button type="submit" form="journalSettingsForm" class="btn btn-primary">保存设置</button>
      </div>
    </div>
  </div>

  <!-- 新建文书模板模态框 -->
  <div class="modal-overlay" id="templateModal">
    <div class="modal modal-large">
      <div class="modal-header">
        <div class="modal-title">📝 新建文书模板</div>
        <button class="modal-close" onclick="closeTemplateModal()">×</button>
      </div>
      <div class="modal-body">
        <form id="templateForm" onsubmit="saveTemplate(event)">
          <input type="hidden" name="templateId" id="templateId">
          <div class="form-group">
            <label class="form-label">模板名称 <span class="required">*</span></label>
            <input type="text" class="form-input" name="templateName" id="templateName" placeholder="如：民事起诉状(买卖合同纠纷版)" required>
          </div>
          <div class="form-group">
            <label class="form-label">所属分类 <span class="required">*</span></label>
            <select class="form-select" name="templateCategory" id="templateCategory" required></select>
          </div>
          <div class="form-group">
            <label class="form-label">模板内容 <span class="required">*</span></label>
            <textarea class="form-textarea" name="templateContent" id="templateContent" rows="12" placeholder="请输入文书模板内容，可用【】标注需要填写的部分..." required></textarea>
          </div>
          <div class="form-group">
            <label class="form-label">或导入文件</label>
            <input type="file" class="form-input" accept=".txt,.doc,.docx" onchange="importTemplateFile(event)">
            <p style="font-size: 12px; color: var(--morandi-text-light); margin-top: 4px;">支持导入txt、doc、docx文件内容</p>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" onclick="closeTemplateModal()">取消</button>
        <button type="submit" form="templateForm" class="btn btn-primary">保存模板</button>
      </div>
    </div>
  </div>

  <!-- 新建分类模态框 -->
  <div class="modal-overlay" id="categoryModal">
    <div class="modal">
      <div class="modal-header">
        <div class="modal-title">📁 新建分类</div>
        <button class="modal-close" onclick="closeCategoryModal()">×</button>
      </div>
      <div class="modal-body">
        <form id="categoryForm" onsubmit="saveCategory(event)">
          <div class="form-group">
            <label class="form-label">分类名称 <span class="required">*</span></label>
            <input type="text" class="form-input" name="categoryName" placeholder="如：申请书类、证据类" required>
          </div>
          <div class="form-group">
            <label class="form-label">分类图标</label>
            <select class="form-select" name="categoryIcon">
              <option value="📄">📄 文书</option>
              <option value="📋">📋 申请</option>
              <option value="📑">📑 证据</option>
              <option value="⚖️">⚖️ 答辩</option>
              <option value="📝">📝 代理</option>
              <option value="📌">📌 其他</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label">分类描述</label>
            <textarea class="form-textarea" name="categoryDesc" rows="2" placeholder="简要描述该分类的内容"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" onclick="closeCategoryModal()">取消</button>
        <button type="submit" form="categoryForm" class="btn btn-primary">保存分类</button>
      </div>
    </div>
  </div>

  <!-- 新建日程模态框 -->
  <div class="modal-overlay" id="eventModal">
    <div class="modal">
      <div class="modal-header">
        <div class="modal-title">➕ 新建日程</div>
        <button class="modal-close" onclick="closeEventModal()">×</button>
      </div>
      <div class="modal-body">
        <form id="eventForm" onsubmit="saveEvent(event)">
          <div class="form-group">
            <label class="form-label">日程标题 <span class="required">*</span></label>
            <input type="text" class="form-input" name="eventTitle" placeholder="如：张某案开庭" required>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">日期 <span class="required">*</span></label>
              <input type="date" class="form-input" name="eventDate" required>
            </div>
            <div class="form-group">
              <label class="form-label">时间</label>
              <input type="time" class="form-input" name="eventTime">
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">日程类型</label>
            <select class="form-select" name="eventType">
              <option value="normal">一般日程</option>
              <option value="case">案件相关</option>
              <option value="urgent">紧急事项</option>
              <option value="log">日志截止</option>
            </select>
          </div>
          <div class="form-group">
            <label class="form-label">备注</label>
            <textarea class="form-textarea" name="eventNote" rows="2" placeholder="补充说明"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" onclick="closeEventModal()">取消</button>
        <button type="submit" form="eventForm" class="btn btn-primary">保存日程</button>
      </div>
    </div>
  </div>



  <!-- 模板详情模态框 -->
  <div class="modal-overlay" id="templateDetailModal">
    <div class="modal modal-large">
      <div class="modal-header">
        <div class="modal-title" id="templateDetailTitle">模板详情</div>
        <button class="modal-close" onclick="closeTemplateDetailModal()">×</button>
      </div>
      <div class="modal-body">
        <pre id="templateDetailContent" style="white-space: pre-wrap; font-family: inherit; font-size: 14px; line-height: 1.8; color: var(--morandi-text);"></pre>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-primary" onclick="copyTemplateContent()">复制内容</button>
        <button type="button" class="btn btn-secondary" onclick="closeTemplateDetailModal()">关闭</button>
      </div>
    </div>
  </div>

  <!-- 提示框容器 -->
  <div class="toast-container" id="toastContainer"></div>

  <script>
    // 数据存储
    let cases = JSON.parse(localStorage.getItem('lawyer_cases') || '[]');
    let journals = JSON.parse(localStorage.getItem('lawyer_journals') || '[]');
    let journalSettings = JSON.parse(localStorage.getItem('journal_settings') || '{"target": 80}');
    let templateCategories = JSON.parse(localStorage.getItem('template_categories') || '[{"id":1,"name":"起诉状类","icon":"📄","desc":"各类民事起诉状模板"},{"id":2,"name":"答辩状类","icon":"⚖️","desc":"答辩状、反诉状模板"},{"id":3,"name":"申请书类","icon":"📋","desc":"各类诉讼申请书模板"},{"id":4,"name":"证据类","icon":"📑","desc":"证据清单、质证意见模板"}]');
    let templates = JSON.parse(localStorage.getItem('lawyer_templates') || '[]');
    let events = JSON.parse(localStorage.getItem('lawyer_events') || '[]');


    let currentPage = 'home';
    let draggedCase = null;
    let currentCaseId = null;
    let calendarDate = new Date();
    let currentTemplateCategory = null;

    // 初始化示例数据（每个模块仅保留1条示例，且可删除）
    function initSampleData() {
      if (cases.length === 0) {
        const now = new Date();
        cases = [{
          id: 1,
          caseNo: '(2025)京0105民初1156号',
          caseType: '买卖合同纠纷',
          caseName: '张某买卖合同纠纷示例',
          plaintiff: '张某',
          defendant: '北京某贸易有限公司',
          court: '北京市朝阳区人民法院',
          deadline: formatDate(new Date(now.getTime() + 7 * 24 * 60 * 60 * 1000)),
          urgency: 'normal',
          status: 'trial',
          summary: '这是示例案件，可删除。原告向被告购买货物，被告未按时交货，原告起诉要求支付违约金。',
          createdAt: formatDate(now),
          timeline: [{ date: '2025-04-10', content: '立案受理' }, { date: '2025-05-12', content: '第一次开庭' }],
          isSample: true
        }];
        saveCases();
      }

      if (journals.length === 0) {
        journals = [{
          id: 1,
          date: formatDate(new Date()),
          week: '第1周',
          content: '这是第一篇示例实习日志，可删除。今天在指导律师的带领下，学习了民事诉讼的基本流程，包括立案、送达、举证、开庭等环节。通过本次学习，我对民事诉讼程序有了更深入的理解。',
          tags: ['民事诉讼', '立案', '学习'],
          createdAt: Date.now(),
          isSample: true
        }];
        saveJournals();
      }

      if (templates.length === 0) {
        templates = [{
          id: 1,
          name: '民事起诉状示例（可删除）',
          category: 1,
          content: '民事起诉状\n\n原告：【姓名】，【性别】，【民族】，【出生日期】，住址：【详细地址】，身份证号：【号码】，联系电话：【电话】\n\n被告：【名称】，住所地：【地址】，统一社会信用代码：【代码】\n法定代表人：【姓名】，职务：【职务】，联系电话：【电话】\n\n诉讼请求：\n1. 判令被告支付原告货款人民币【金额】元；\n2. 判令被告支付违约金人民币【金额】元；\n3. 判令被告承担本案诉讼费用。\n\n事实与理由：\n【详细陈述案件事实和理由】\n\n综上所述，为维护原告的合法权益，特向贵院提起诉讼，请求依法判决。\n\n此致\n【法院名称】\n\n具状人：【签名】\n【日期】',
          createdAt: Date.now(),
          isSample: true
        }];
        saveTemplates();
      }

    }

    // 数据保存函数
    function saveCases() { localStorage.setItem('lawyer_cases', JSON.stringify(cases)); }
    function saveJournals() { localStorage.setItem('lawyer_journals', JSON.stringify(journals)); }
    function saveTemplates() { localStorage.setItem('lawyer_templates', JSON.stringify(templates)); updateTemplateStats(); }

    // 格式化日期
    function formatDate(date) {
      const y = date.getFullYear();
      const m = String(date.getMonth() + 1).padStart(2, '0');
      const d = String(date.getDate()).padStart(2, '0');
      return `${y}-${m}-${d}`;
    }

    // 页面导航
    function navigate(page) {
      currentPage = page;
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById('page-' + page).classList.add('active');
      document.querySelectorAll('.nav-item').forEach(item => item.classList.remove('active'));
      event.currentTarget.classList.add('active');
      if (page === 'board') renderBoard();
      if (page === 'journal') renderJournals();
      if (page === 'templates') renderTemplateCategories();
      if (page === 'calendar') renderCalendar();
    }

    // 渲染统计数据
    function renderStats() {
      document.getElementById('statTotal').textContent = cases.length;
      document.getElementById('statUrgent').textContent = cases.filter(c => {
        const days = Math.ceil((new Date(c.deadline) - new Date()) / (1000 * 60 * 60 * 24));
        return days <= 7 && c.status !== 'archived';
      }).length;
      document.getElementById('statDocs').textContent = cases.filter(c => c.status !== 'archived').length;
      document.getElementById('journalCount').textContent = journals.length;
      document.getElementById('templateCount').textContent = templates.length;
    }

    // 渲染图表图例
    function renderChartLegend() {
      const statusLabels = {
        filing: { name: '立案中', color: 'var(--morandi-blue)' },
        preparation: { name: '准备中', color: 'var(--morandi-green)' },
        trial: { name: '审理中', color: '#A89070' },
        closing: { name: '结案中', color: 'var(--morandi-pink)' },
        archived: { name: '已归档', color: 'var(--morandi-gray)' }
      };
      let html = '';
      Object.entries(statusLabels).forEach(([status, label]) => {
        const count = cases.filter(c => c.status === status).length;
        html += `<div class="chart-legend-item"><div class="chart-legend-left"><div class="chart-legend-dot" style="background:${label.color}"></div>${label.name}</div><div class="chart-legend-count">${count} 件</div></div>`;
      });
      document.getElementById('chartLegend').innerHTML = html;
      document.getElementById('chartTotal').textContent = cases.length;
    }

    // 渲染首页待办
    function renderHomeTodos() {
      const urgencyColors = { urgent: 'urgent', important: 'important', normal: 'normal' };
      let html = '';
      const todayStr = formatDate(new Date());
      const todayEvents = events.filter(e => e.date === todayStr).slice(0, 3);

      if (todayEvents.length === 0) {
        html = '<div class="no-cases">今日暂无待办事项</div>';
      } else {
        todayEvents.forEach(e => {
          html += `<div class="todo-item"><div class="todo-dot ${urgencyColors[e.type] || 'normal'}"></div><div class="todo-content"><div class="todo-title">${e.title}</div><div class="todo-meta">${e.time || '全天'}</div></div></div>`;
        });
      }
      document.getElementById('homeTodos').innerHTML = html;
    }

    // 渲染侧边栏案件
    function renderSidebarCases() {
      const recentCases = cases.filter(c => c.status !== 'archived').slice(0, 3);
      const statusColors = { filing: 'normal', preparation: 'normal', trial: 'urgent', closing: 'done', archived: 'done' };
      let html = '';
      if (recentCases.length === 0) {
        html = '<div class="no-cases">点击"新建案件"添加</div>';
      } else {
        recentCases.forEach(c => {
          html += `<div class="quick-case-item ${statusColors[c.status]}" onclick="openCaseDetail(${c.id})"><div class="quick-case-name">${c.caseName}</div><div class="quick-case-meta">${c.deadline}</div></div>`;
        });
      }
      document.getElementById('sidebarCases').innerHTML = html;
    }

    // 渲染看板
    function renderBoard() {
      const statuses = ['filing', 'preparation', 'trial', 'closing', 'archived'];
      const urgencyLabels = { urgent: '紧急', important: '重要', normal: '正常' };
      const filterType = document.getElementById('filterType').value;
      const filterUrgency = document.getElementById('filterUrgency').value;

      statuses.forEach(status => {
        let statusCases = cases.filter(c => c.status === status);
        if (filterType) statusCases = statusCases.filter(c => c.caseType === filterType);
        if (filterUrgency) statusCases = statusCases.filter(c => c.urgency === filterUrgency);

        let html = '';
        if (statusCases.length === 0) {
          html = `<div class="empty-state"><div class="empty-state-icon">📭</div><div class="empty-state-text">暂无案件</div><div class="empty-state-hint">拖拽卡片来变更状态</div></div>`;
        } else {
          statusCases.forEach(c => {
            const daysToDeadline = Math.ceil((new Date(c.deadline) - new Date()) / (1000 * 60 * 60 * 24));
            const isSoon = daysToDeadline <= 3;
            html += `<div class="board-card ${c.urgency}" draggable="true" ondragstart="handleDragStart(event, ${c.id})" ondragend="handleDragEnd(event)" onclick="openCaseDetail(${c.id})"><div class="board-card-top"><span class="board-card-urgency ${c.urgency}">${urgencyLabels[c.urgency]}</span><span class="board-card-deadline ${isSoon ? 'soon' : ''}">${c.deadline}</span></div><div class="board-card-case-no">${c.caseNo}</div><div class="board-card-name">${c.caseName}</div><div class="board-card-party">${c.plaintiff} vs ${c.defendant}</div><div class="board-card-actions"><button class="btn btn-secondary btn-small" onclick="event.stopPropagation();openCaseDetail(${c.id})">详情</button><button class="btn btn-secondary btn-small" onclick="event.stopPropagation();deleteCase(${c.id})">删除</button></div></div>`;
          });
        }
        document.getElementById('col-' + status).innerHTML = html;
        document.getElementById('count-' + status).textContent = statusCases.length;
        document.getElementById('foot-' + status).textContent = statusCases.length;
      });
    }

    // 过滤案件
    function filterCases() { renderBoard(); }

    // 拖拽功能
    function handleDragStart(e, caseId) { draggedCase = caseId; e.target.classList.add('dragging'); }
    function handleDragEnd(e) { e.target.classList.remove('dragging'); }

    function setupDragDrop() {
      document.querySelectorAll('.board-column').forEach(col => {
        col.addEventListener('dragover', e => { e.preventDefault(); col.style.background = 'rgba(154,173,189,0.15)'; });
        col.addEventListener('dragleave', () => { col.style.background = 'rgba(255,255,255,0.6)'; });
        col.addEventListener('drop', e => {
          e.preventDefault();
          col.style.background = 'rgba(255,255,255,0.6)';
          if (draggedCase) {
            const newStatus = col.dataset.status;
            const c = cases.find(x => x.id === draggedCase);
            if (c) { c.status = newStatus; saveCases(); renderAll(); showToast('案件状态已更新', 'success'); }
            draggedCase = null;
          }
        });
      });
    }

    // 案件模态框
    function openCaseModal() {
      document.getElementById('caseModal').classList.add('show');
      document.getElementById('caseForm').reset();
      const deadlineInput = document.querySelector('input[name="deadline"]');
      if (deadlineInput) {
        const date = new Date(); date.setDate(date.getDate() + 7);
        deadlineInput.value = formatDate(date);
      }
    }
    function closeCaseModal() { document.getElementById('caseModal').classList.remove('show'); }

    // 案件详情
    function openCaseDetail(caseId) {
      currentCaseId = caseId;
      const c = cases.find(x => x.id === caseId);
      if (!c) return;
      const statusLabels = { filing: '立案中', preparation: '准备中', trial: '审理中', closing: '结案中', archived: '已归档' };
      const statusColors = { filing: '#9AADBD', preparation: '#A8B5A0', trial: '#A89070', closing: '#C4A7A0', archived: '#9E9E9E' };
      const urgencyLabels = { urgent: '紧急', important: '重要', normal: '正常' };

      let timelineHtml = '';
      if (c.timeline && c.timeline.length > 0) {
        timelineHtml = '<div class="timeline">';
        c.timeline.forEach(t => { timelineHtml += `<div class="timeline-item"><div class="timeline-date">${t.date}</div><div class="timeline-content">${t.content}</div></div>`; });
        timelineHtml += '</div>';
      }

      const html = `<div class="detail-section"><div class="detail-section-title">基本信息</div><div class="detail-row"><div class="detail-label">案号</div><div class="detail-value">${c.caseNo}</div></div><div class="detail-row"><div class="detail-label">案件类型</div><div class="detail-value">${c.caseType}</div></div><div class="detail-row"><div class="detail-label">案件名称</div><div class="detail-value">${c.caseName}</div></div><div class="detail-row"><div class="detail-label">受理法院</div><div class="detail-value">${c.court || '-'}</div></div><div class="detail-row"><div class="detail-label">当前状态</div><div class="detail-value"><span class="tag" style="background:${statusColors[c.status]}20;color:${statusColors[c.status]}">${statusLabels[c.status]}</span></div></div><div class="detail-row"><div class="detail-label">紧急程度</div><div class="detail-value">${urgencyLabels[c.urgency]}</div></div><div class="detail-row"><div class="detail-label">截止日期</div><div class="detail-value">${c.deadline}</div></div></div><div class="detail-section"><div class="detail-section-title">当事人信息</div><div class="detail-row"><div class="detail-label">原告</div><div class="detail-value">${c.plaintiff || '-'}</div></div><div class="detail-row"><div class="detail-label">被告</div><div class="detail-value">${c.defendant || '-'}</div></div></div><div class="detail-section"><div class="detail-section-title">案情摘要</div><div style="font-size:14px;line-height:1.8">${c.summary || '暂无摘要'}</div></div><div class="detail-section"><div class="detail-section-title">案件进展</div>${timelineHtml || '<div style="font-size:13px;color:var(--morandi-text-light)">暂无进展记录</div>'}</div>`;

      document.getElementById('detailContent').innerHTML = html;
      document.getElementById('detailModal').classList.add('show');
    }
    function closeDetailModal() { document.getElementById('detailModal').classList.remove('show'); currentCaseId = null; }

    // 保存案件
    function saveCase(e) {
      e.preventDefault();
      const formData = new FormData(e.target);
      const newCase = {
        id: Date.now(),
        caseNo: formData.get('caseNo'),
        caseType: formData.get('caseType'),
        caseName: formData.get('caseName'),
        plaintiff: formData.get('plaintiff') || '',
        defendant: formData.get('defendant') || '',
        court: formData.get('court') || '',
        deadline: formData.get('deadline'),
        urgency: formData.get('urgency'),
        status: formData.get('status'),
        summary: formData.get('summary') || '',
        createdAt: formatDate(new Date()),
        timeline: [{ date: formatDate(new Date()), content: '案件创建' }]
      };
      cases.push(newCase);
      saveCases();
      closeCaseModal();
      renderAll();
      showToast('案件创建成功', 'success');
    }

    // 删除案件
    function deleteCase(caseId) {
      if (confirm('确定要删除这个案件吗？')) {
        cases = cases.filter(c => c.id !== caseId);
        saveCases();
        renderAll();
        showToast('案件已删除', 'success');
      }
    }

    function deleteCurrentCase() {
      if (currentCaseId) {
        deleteCase(currentCaseId);
        closeDetailModal();
      }
    }

    // 实习日志功能
    function renderJournals() {
      document.getElementById('journalTotal').textContent = journals.length;
      document.getElementById('journalTarget').textContent = journalSettings.target || '--';
      const progress = journalSettings.target ? Math.min(100, Math.round((journals.length / journalSettings.target) * 100)) : 0;
      document.getElementById('journalProgress').textContent = progress + '%';
      document.getElementById('journalProgressBar').style.width = progress + '%';

      const sortedJournals = [...journals].sort((a, b) => new Date(b.date) - new Date(a.date));
      let html = '';
      if (sortedJournals.length === 0) {
        html = `<div class="empty-state"><div class="empty-state-icon">📓</div><div class="empty-state-text">还没有实习日志</div><div class="empty-state-hint">点击上方按钮开始写第一篇日志</div></div>`;
      } else {
        sortedJournals.forEach(j => {
          const tagsHtml = j.tags && j.tags.length ? j.tags.map(t => `<span class="journal-item-tag">${t}</span>`).join('') : '';
          html += `<div class="journal-item"><div class="journal-item-header"><div class="journal-item-date">📅 ${j.date} ${j.week ? '· ' + j.week : ''}</div><div class="journal-item-actions"><button class="btn btn-secondary btn-small" onclick="editJournal(${j.id})">编辑</button><button class="btn btn-secondary btn-small" onclick="deleteJournal(${j.id})">删除</button></div></div><div class="journal-item-content">${j.content.replace(/\n/g, '<br>')}</div><div class="journal-item-tags">${tagsHtml}</div></div>`;
        });
      }
      document.getElementById('journalList').innerHTML = html;
    }

    function openJournalModal(isEdit = false) {
      document.getElementById('journalModal').classList.add('show');
      if (!isEdit) {
        document.getElementById('journalForm').reset();
        document.getElementById('journalId').value = '';
        document.getElementById('journalDate').value = formatDate(new Date());
      }
    }
    function closeJournalModal() { document.getElementById('journalModal').classList.remove('show'); }

    function saveJournal(e) {
      e.preventDefault();
      const formData = new FormData(e.target);
      const journalId = formData.get('journalId');
      const tagsStr = formData.get('journalTags') || '';
      const tags = tagsStr.split(/[,，]/).map(t => t.trim()).filter(t => t);

      const journalData = {
        date: formData.get('journalDate'),
        week: formData.get('journalWeek'),
        content: formData.get('journalContent'),
        tags: tags
      };

      if (journalId) {
        const index = journals.findIndex(j => j.id === parseInt(journalId));
        if (index !== -1) {
          journals[index] = { ...journals[index], ...journalData };
          showToast('日志更新成功', 'success');
        }
      } else {
        journals.push({ id: Date.now(), ...journalData, createdAt: Date.now() });
        showToast('日志保存成功', 'success');
      }

      saveJournals();
      closeJournalModal();
      renderJournals();
      renderStats();
    }

    function editJournal(journalId) {
      const j = journals.find(x => x.id === journalId);
      if (!j) return;
      document.getElementById('journalId').value = j.id;
      document.getElementById('journalDate').value = j.date;
      document.getElementById('journalWeek').value = j.week || '';
      document.getElementById('journalContent').value = j.content;
      document.getElementById('journalTags').value = j.tags ? j.tags.join(', ') : '';
      openJournalModal(true);
    }

    function deleteJournal(journalId) {
      if (confirm('确定要删除这篇日志吗？')) {
        journals = journals.filter(j => j.id !== journalId);
        saveJournals();
        renderJournals();
        renderStats();
        showToast('日志已删除', 'success');
      }
    }

    function openJournalSettings() {
      document.getElementById('journalSettingsModal').classList.add('show');
      document.getElementById('journalTargetInput').value = journalSettings.target || '';
    }
    function closeJournalSettingsModal() { document.getElementById('journalSettingsModal').classList.remove('show'); }

    function saveJournalSettings(e) {
      e.preventDefault();
      const formData = new FormData(e.target);
      journalSettings.target = parseInt(formData.get('journalTarget'));
      localStorage.setItem('journal_settings', JSON.stringify(journalSettings));
      closeJournalSettingsModal();
      renderJournals();
      showToast('设置已保存', 'success');
    }

    // 文书模板功能
    function updateTemplateStats() {
      document.getElementById('templateCount').textContent = templates.length;
    }

    function renderTemplateCategories() {
      let html = '';
      templateCategories.forEach(cat => {
        const catTemplates = templates.filter(t => t.category === cat.id);
        html += `<div class="template-category" onclick="openTemplateCategory(${cat.id})"><div class="template-category-header"><div class="template-category-title">${cat.icon} ${cat.name}</div><div class="template-category-count">${catTemplates.length} 个模板</div></div><div class="template-category-desc">${cat.desc || ''}</div></div>`;
      });
      document.getElementById('templateCategories').innerHTML = html;
      document.getElementById('templateCategoriesContainer').classList.remove('hidden');
      document.getElementById('templateListContainer').classList.add('hidden');
    }

    function openTemplateCategory(categoryId) {
      currentTemplateCategory = categoryId;
      const cat = templateCategories.find(c => c.id === categoryId);
      const catTemplates = templates.filter(t => t.category === categoryId);

      document.getElementById('templatePageTitle').textContent = `📝 ${cat.name}`;
      document.getElementById('templateCategoriesContainer').classList.add('hidden');
      document.getElementById('templateListContainer').classList.remove('hidden');

      let html = '';
      if (catTemplates.length === 0) {
        html = `<div class="empty-state"><div class="empty-state-icon">📄</div><div class="empty-state-text">该分类暂无模板</div><div class="empty-state-hint">点击上方按钮添加第一个模板</div></div>`;
      } else {
        catTemplates.forEach(t => {
          html += `<div class="template-item" onclick="openTemplateDetail(${t.id})"><div class="template-item-title">${t.name}</div><div class="template-item-actions"><button class="btn btn-secondary btn-small" onclick="event.stopPropagation();editTemplate(${t.id})">编辑</button><button class="btn btn-secondary btn-small" onclick="event.stopPropagation();deleteTemplate(${t.id})">删除</button></div></div>`;
        });
      }
      document.getElementById('templateList').innerHTML = html;
    }

    function backToTemplateCategories() {
      currentTemplateCategory = null;
      document.getElementById('templatePageTitle').textContent = '📝 文书模板库';
      renderTemplateCategories();
    }

    function openTemplateModal() {
      document.getElementById('templateModal').classList.add('show');
      document.getElementById('templateForm').reset();
      document.getElementById('templateId').value = '';
      const select = document.getElementById('templateCategory');
      select.innerHTML = templateCategories.map(c => `<option value="${c.id}">${c.icon} ${c.name}</option>`).join('');
      if (currentTemplateCategory) select.value = currentTemplateCategory;
    }
    function closeTemplateModal() { document.getElementById('templateModal').classList.remove('show'); }

    function saveTemplate(e) {
      e.preventDefault();
      const formData = new FormData(e.target);
      const templateId = formData.get('templateId');
      const templateData = {
        name: formData.get('templateName'),
        category: parseInt(formData.get('templateCategory')),
        content: formData.get('templateContent')
      };

      if (templateId) {
        const index = templates.findIndex(t => t.id === parseInt(templateId));
        if (index !== -1) {
          templates[index] = { ...templates[index], ...templateData };
          showToast('模板更新成功', 'success');
        }
      } else {
        templates.push({ id: Date.now(), ...templateData, createdAt: Date.now() });
        showToast('模板创建成功', 'success');
      }

      saveTemplates();
      closeTemplateModal();
      if (currentTemplateCategory) {
        openTemplateCategory(currentTemplateCategory);
      } else {
        renderTemplateCategories();
      }
    }

    function editTemplate(templateId) {
      const t = templates.find(x => x.id === templateId);
      if (!t) return;
      document.getElementById('templateId').value = t.id;
      document.getElementById('templateName').value = t.name;
      document.getElementById('templateContent').value = t.content;
      const select = document.getElementById('templateCategory');
      select.innerHTML = templateCategories.map(c => `<option value="${c.id}">${c.icon} ${c.name}</option>`).join('');
      select.value = t.category;
      openTemplateModal();
    }

    function deleteTemplate(templateId) {
      if (confirm('确定要删除这个模板吗？')) {
        templates = templates.filter(t => t.id !== templateId);
        saveTemplates();
        if (currentTemplateCategory) {
          openTemplateCategory(currentTemplateCategory);
        } else {
          renderTemplateCategories();
        }
        showToast('模板已删除', 'success');
      }
    }

    function openTemplateDetail(templateId) {
      const t = templates.find(x => x.id === templateId);
      if (!t) return;
      document.getElementById('templateDetailTitle').textContent = t.name;
      document.getElementById('templateDetailContent').textContent = t.content;
      document.getElementById('templateDetailModal').classList.add('show');
    }
    function closeTemplateDetailModal() { document.getElementById('templateDetailModal').classList.remove('show'); }

    function copyTemplateContent() {
      const content = document.getElementById('templateDetailContent').textContent;
      navigator.clipboard.writeText(content).then(() => {
        showToast('内容已复制到剪贴板', 'success');
      }).catch(() => {
        showToast('复制失败，请手动复制', 'error');
      });
    }

    function openCategoryModal() {
      document.getElementById('categoryModal').classList.add('show');
      document.getElementById('categoryForm').reset();
    }
    function closeCategoryModal() { document.getElementById('categoryModal').classList.remove('show'); }

    function saveCategory(e) {
      e.preventDefault();
      const formData = new FormData(e.target);
      const newCategory = {
        id: Date.now(),
        name: formData.get('categoryName'),
        icon: formData.get('categoryIcon'),
        desc: formData.get('categoryDesc') || ''
      };
      templateCategories.push(newCategory);
      localStorage.setItem('template_categories', JSON.stringify(templateCategories));
      closeCategoryModal();
      renderTemplateCategories();
      showToast('分类创建成功', 'success');
    }

    function importTemplateFile(e) {
      const file = e.target.files[0];
      if (!file) return;
      const reader = new FileReader();
      reader.onload = function(e) {
        document.getElementById('templateContent').value = e.target.result;
        showToast('文件内容已导入', 'success');
      };
      reader.readAsText(file);
    }



    // 日历功能
    function renderCalendar() {
      const year = calendarDate.getFullYear();
      const month = calendarDate.getMonth();
      document.getElementById('calendarTitle').textContent = `${year}年${month + 1}月`;

      const firstDay = new Date(year, month, 1);
      const lastDay = new Date(year, month + 1, 0);
      const startDay = firstDay.getDay();
      const daysInMonth = lastDay.getDate();

      const today = new Date();
      const todayStr = formatDate(today);

      let html = '';
      for (let i = 0; i < startDay; i++) {
        const prevDate = new Date(year, month, -startDay + i + 1);
        html += `<div class="calendar-day other-month"><div class="calendar-day-number">${prevDate.getDate()}</div></div>`;
      }

      for (let day = 1; day <= daysInMonth; day++) {
        const dateStr = `${year}-${String(month + 1).padStart(2, '0')}-${String(day).padStart(2, '0')}`;
        const dayEvents = events.filter(e => e.date === dateStr);
        const isToday = dateStr === todayStr;

        html += `<div class="calendar-day ${isToday ? 'today' : ''}" onclick="openDayEvents('${dateStr}')"><div class="calendar-day-number">${day}</div>`;

        dayEvents.slice(0, 3).forEach(e => {
          const eventClass = e.type === 'urgent' ? 'urgent' : e.type === 'case' ? 'case' : e.type === 'log' ? 'log' : '';
          html += `<div class="calendar-event ${eventClass}">${e.time ? e.time + ' ' : ''}${e.title}</div>`;
        });

        if (dayEvents.length > 3) {
          html += `<div class="calendar-event-more">+${dayEvents.length - 3} 更多</div>`;
        }

        html += '</div>';
      }

      const remainingDays = 42 - (startDay + daysInMonth);
      for (let i = 1; i <= remainingDays; i++) {
        html += `<div class="calendar-day other-month"><div class="calendar-day-number">${i}</div></div>`;
      }

      document.getElementById('calendarDays').innerHTML = html;
    }

    function prevMonth() { calendarDate.setMonth(calendarDate.getMonth() - 1); renderCalendar(); }
    function nextMonth() { calendarDate.setMonth(calendarDate.getMonth() + 1); renderCalendar(); }

    function openEventModal() {
      document.getElementById('eventModal').classList.add('show');
      document.getElementById('eventForm').reset();
      document.querySelector('input[name="eventDate"]').value = formatDate(new Date());
    }
    function closeEventModal() { document.getElementById('eventModal').classList.remove('show'); }

    function saveEvent(e) {
      e.preventDefault();
      const formData = new FormData(e.target);
      const newEvent = {
        id: Date.now(),
        title: formData.get('eventTitle'),
        date: formData.get('eventDate'),
        time: formData.get('eventTime') || '',
        type: formData.get('eventType'),
        note: formData.get('eventNote') || ''
      };
      events.push(newEvent);
      localStorage.setItem('lawyer_events', JSON.stringify(events));
      closeEventModal();
      renderCalendar();
      renderHomeTodos();
      showToast('日程创建成功', 'success');
    }

    function openDayEvents(dateStr) {
      const dayEvents = events.filter(e => e.date === dateStr);
      if (dayEvents.length === 0) {
        document.querySelector('input[name="eventDate"]').value = dateStr;
        openEventModal();
      } else {
        alert(`${dateStr} 的日程：\n` + dayEvents.map(e => `${e.time || '全天'} - ${e.title}`).join('\n'));
      }
    }

    // 通用提示框
    function showToast(message, type = 'info') {
      const container = document.getElementById('toastContainer');
      const toast = document.createElement('div');
      toast.className = `toast ${type}`;
      const icons = { success: '✓', error: '✗', info: 'ℹ' };
      toast.innerHTML = `<span>${icons[type] || 'ℹ'}</span> ${message}`;
      container.appendChild(toast);
      setTimeout(() => {
        toast.style.opacity = '0'; toast.style.transform = 'translateX(100%)';
        setTimeout(() => toast.remove(), 300);
      }, 2500);
    }

    // 渲染所有
    function renderAll() { renderStats(); renderChartLegend(); renderHomeTodos(); renderSidebarCases(); renderBoard(); }

    // 初始化
    initSampleData();
    renderAll();
    setupDragDrop();

    // 快捷键
    document.addEventListener('keydown', e => {
      if (e.key === 'Escape') {
        closeCaseModal(); closeDetailModal(); closeJournalModal();
        closeJournalSettingsModal(); closeTemplateModal(); closeCategoryModal();
        closeEventModal(); closeKnowledgeModal(); closeKnowledgeDetailModal(); closeTemplateDetailModal();
      }
      if (e.ctrlKey && e.key === 'k') { e.preventDefault(); document.getElementById('globalSearch').focus(); }
    });
  </script>
</body>
</html>
</think_never_used_51bce0c785ca2f68081bfa7d91973934>
