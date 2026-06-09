<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>🛒 Lista de la Compra</title>
  <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --green: #22c55e; --green-dk: #16a34a;
      --bg: #f0fdf4; --surface: #ffffff;
      --border: #d1fae5; --text: #14532d;
      --muted: #6b7280; --danger: #ef4444;
      --shadow: 0 2px 12px rgba(0,0,0,.07);
    }
    body { font-family: 'Segoe UI', system-ui, sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; }
    header { background: var(--surface); border-bottom: 1px solid var(--border); padding: 18px 32px; display: flex; align-items: center; gap: 12px; box-shadow: var(--shadow); }
    header h1 { font-size: 22px; font-weight: 700; }
    .dot { width: 10px; height: 10px; border-radius: 50%; background: var(--green); }
    .app { display: flex; height: calc(100vh - 61px); }

    /* SIDEBAR */
    .sidebar { width: 280px; min-width: 220px; background: var(--surface); border-right: 1px solid var(--border); display: flex; flex-direction: column; overflow: hidden; }
    .sidebar-header { padding: 18px 16px 12px; border-bottom: 1px solid var(--border); }
    .sidebar-header p { font-size: 11px; text-transform: uppercase; letter-spacing: .08em; color: var(--muted); margin-bottom: 10px; font-weight: 600; }
    .new-list-row { display: flex; gap: 6px; }
    .new-list-row input { flex: 1; border: 1.5px solid var(--border); border-radius: 8px; padding: 8px 10px; font-size: 13px; outline: none; color: var(--text); transition: border-color .15s; }
    .new-list-row input:focus { border-color: var(--green); }
    .new-list-row button { background: var(--green); color: #fff; border: none; border-radius: 8px; padding: 8px 12px; font-size: 16px; cursor: pointer; transition: background .15s; }
    .new-list-row button:hover { background: var(--green-dk); }
    .lists-scroll { flex: 1; overflow-y: auto; padding: 8px; }
    .list-item { display: flex; align-items: center; padding: 10px 12px; border-radius: 10px; cursor: pointer; margin-bottom: 4px; transition: background .12s; border: 1.5px solid transparent; }
    .list-item:hover { background: #f0fdf4; }
    .list-item.active { background: #dcfce7; border-color: var(--green); }
    .list-item .list-icon { font-size: 18px; margin-right: 10px; }
    .list-item .list-name { flex: 1; font-size: 14px; font-weight: 500; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
    .list-item .list-count { font-size: 11px; background: #bbf7d0; color: var(--green-dk); border-radius: 20px; padding: 1px 7px; font-weight: 600; margin-right: 6px; }
    .list-item .del-list { opacity: 0; background: none; border: none; color: var(--danger); cursor: pointer; font-size: 14px; padding: 2px 4px; border-radius: 4px; transition: opacity .12s; }
    .list-item:hover .del-list { opacity: 1; }
    .empty-lists { text-align: center; padding: 40px 16px; color: var(--muted); font-size: 13px; }
    .empty-lists .big { font-size: 40px; margin-bottom: 8px; }

    /* MAIN */
    .main { flex: 1; display: flex; flex-direction: column; overflow: hidden; }
    .main-empty { flex: 1; display: flex; flex-direction: column; align-items: center; justify-content: center; color: var(--muted); gap: 10px; }
    .main-empty .big { font-size: 60px; }
    .main-header { padding: 20px 28px 16px; border-bottom: 1px solid var(--border); background: var(--surface); display: flex; align-items: center; gap: 12px; }
    .main-header h2 { font-size: 20px; font-weight: 700; flex: 1; }
    .progress-pill { font-size: 12px; background: #dcfce7; color: var(--green-dk); border-radius: 20px; padding: 3px 10px; font-weight: 600; }
    .progress-bar-wrap { height: 4px; background: var(--border); margin: 0 28px; }
    .progress-bar { height: 4px; background: var(--green); transition: width .4s ease; border-radius: 2px; }

    /* ADD ITEM */
    .add-item-row { display: flex; gap: 8px; padding: 16px 28px; border-bottom: 1px solid var(--border); background: var(--surface); }
    .search-wrap { position: relative; flex: 1; }
    .search-wrap input { width: 100%; border: 1.5px solid var(--border); border-radius: 10px; padding: 10px 14px; font-size: 14px; outline: none; color: var(--text); transition: border-color .15s; }
    .search-wrap input:focus { border-color: var(--green); }
    .add-item-row button { background: var(--green); color: #fff; border: none; border-radius: 10px; padding: 10px 20px; font-size: 14px; font-weight: 600; cursor: pointer; transition: background .15s; white-space: nowrap; }
    .add-item-row button:hover { background: var(--green-dk); }

    /* DROPDOWN */
    .dropdown { position: absolute; top: calc(100% + 6px); left: 0; right: 0; background: white; border: 1.5px solid var(--border); border-radius: 12px; box-shadow: 0 8px 28px rgba(0,0,0,.13); z-index: 200; max-height: 320px; overflow-y: auto; }
    .dropdown-item { display: flex; align-items: center; gap: 10px; padding: 10px 14px; cursor: pointer; border-bottom: 1px solid #f0fdf4; transition: background .1s; }
    .dropdown-item:last-child { border-bottom: none; }
    .dropdown-item:hover, .dropdown-item.active { background: #f0fdf4; }
    .dropdown-item img { width: 40px; height: 40px; object-fit: contain; border-radius: 6px; border: 1px solid var(--border); flex-shrink: 0; }
    .dropdown-item .no-img { width: 40px; height: 40px; border-radius: 6px; border: 1px solid var(--border); background: #f9fafb; display: flex; align-items: center; justify-content: center; font-size: 20px; flex-shrink: 0; }
    .dropdown-item .prod-info { flex: 1; min-width: 0; }
    .dropdown-item .prod-name { font-size: 13px; font-weight: 500; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
    .dropdown-item .prod-sub { font-size: 11px; color: var(--muted); margin-top: 2px; }
    .dropdown-item .prod-price { font-size: 13px; color: var(--green-dk); font-weight: 700; flex-shrink: 0; }
    .dropdown-loading, .dropdown-empty { padding: 14px 16px; font-size: 13px; color: var(--muted); text-align: center; }

    /* ITEMS */
    .items-scroll { flex: 1; overflow-y: auto; padding: 16px 28px; }
    .item-row { display: flex; align-items: center; gap: 12px; padding: 12px 14px; border-radius: 10px; border: 1.5px solid transparent; cursor: pointer; margin-bottom: 6px; transition: background .12s, border-color .12s; background: var(--surface); box-shadow: var(--shadow); }
    .item-row:hover { border-color: var(--border); }
    .item-row.checked { background: #f9fafb; box-shadow: none; }
    .item-thumb { width: 36px; height: 36px; object-fit: contain; border-radius: 6px; border: 1px solid var(--border); flex-shrink: 0; }
    .item-no-thumb { width: 36px; height: 36px; border-radius: 6px; background: #f0fdf4; display: flex; align-items: center; justify-content: center; font-size: 18px; flex-shrink: 0; }
    .checkbox { width: 22px; height: 22px; border-radius: 6px; border: 2px solid #d1d5db; display: flex; align-items: center; justify-content: center; flex-shrink: 0; transition: background .15s, border-color .15s; font-size: 13px; }
    .item-row.checked .checkbox { background: var(--green); border-color: var(--green); color: #fff; }
    .item-info { flex: 1; min-width: 0; }
    .item-name { font-size: 14px; }
    .item-price { font-size: 11px; color: var(--green-dk); font-weight: 600; margin-top: 1px; }
    .item-row.checked .item-name { text-decoration: line-through; color: var(--muted); }
    .item-row.checked .item-price { color: var(--muted); }
    .del-item { opacity: 0; background: none; border: none; color: var(--danger); cursor: pointer; font-size: 15px; padding: 3px 6px; border-radius: 5px; transition: opacity .12s; }
    .item-row:hover .del-item { opacity: 1; }
    .items-empty { text-align: center; padding: 60px 16px; color: var(--muted); font-size: 14px; }
    .items-empty .big { font-size: 48px; margin-bottom: 8px; }

    .loader { display: inline-block; width: 18px; height: 18px; border: 2px solid var(--border); border-top-color: var(--green); border-radius: 50%; animation: spin .6s linear infinite; }
    @keyframes spin { to { transform: rotate(360deg); } }
    #toast { position: fixed; bottom: 24px; right: 24px; background: #1a1a2e; color: #fff; padding: 10px 18px; border-radius: 10px; font-size: 13px; opacity: 0; transform: translateY(10px); transition: opacity .2s, transform .2s; pointer-events: none; z-index: 999; }
    #toast.show { opacity: 1; transform: translateY(0); }
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-thumb { background: #d1fae5; border-radius: 3px; }
    @media (max-width: 600px) {
      .sidebar { width: 200px; min-width: 160px; }
      .main-header, .add-item-row, .items-scroll { padding-left: 14px; padding-right: 14px; }
    }
  </style>
</head>
<body>

<header>
  <div class="dot"></div>
  <h1>Lista de la Compra</h1>
</header>

<div class="app">
  <aside class="sidebar">
    <div class="sidebar-header">
      <p>Mis Listas</p>
      <div class="new-list-row">
        <input id="input-new-list" placeholder="Nueva lista…" maxlength="40" />
        <button onclick="createList()" title="Crear">+</button>
      </div>
    </div>
    <div class="lists-scroll" id="lists-container">
      <div class="empty-lists"><div class="big">🛒</div><span>Crea tu primera lista</span></div>
    </div>
  </aside>

  <main class="main" id="main">
    <div class="main-empty"><div class="big">👈</div><p>Selecciona o crea una lista</p></div>
  </main>
</div>

<div id="toast"></div>

<script>
  const SUPABASE_URL = 'https://zmckywsgbdhchsesyxch.supabase.co';
  const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InptY2t5d3NnYmRoY2hzZXN5eGNoIiwicm9sZSI6ImFub24iLCJpYXQiOjE3ODEwMTg0NDAsImV4cCI6MjA5NjU5NDQ0MH0.tr2m8axJNfWlXp85WgjiWkw2gei0UkhwGG4xdX-qRyk';

  const { createClient } = supabase;
  const sb = createClient(SUPABASE_URL, SUPABASE_KEY);

  let lists = [], activeList = null, items = [];
  let searchTimeout = null, dropdownResults = [], dropdownIndex = -1;

  /* ── TOAST ── */
  function toast(msg) {
    const el = document.getElementById('toast');
    el.textContent = msg;
    el.classList.add('show');
    setTimeout(() => el.classList.remove('show'), 2200);
  }

  /* ── LISTS ── */
  async function loadLists() {
    const { data, error } = await sb.from('lists').select('*').order('created_at', { ascending: false });
    if (error) { toast('❌ ' + error.message); return; }
    lists = data || [];
    renderSidebar();
  }

  function renderSidebar() {
    const c = document.getElementById('lists-container');
    if (!lists.length) {
      c.innerHTML = `<div class="empty-lists"><div class="big">🛒</div><span>Crea tu primera lista</span></div>`;
      return;
    }
    c.innerHTML = lists.map(l => `
      <div class="list-item ${activeList?.id === l.id ? 'active' : ''}" onclick="selectList('${l.id}')">
        <span class="list-icon">📋</span>
        <span class="list-name">${esc(l.name)}</span>
        ${l._count != null ? `<span class="list-count">${l._count}</span>` : ''}
        <button class="del-list" onclick="deleteList(event,'${l.id}')">✕</button>
      </div>`).join('');
  }

  async function createList() {
    const input = document.getElementById('input-new-list');
    const name = input.value.trim();
    if (!name) return;
    const { data, error } = await sb.from('lists').insert({ name }).select().single();
    if (error) { toast('❌ ' + error.message); return; }
    lists.unshift(data);
    input.value = '';
    renderSidebar();
    selectList(data.id);
    toast('✅ Lista creada');
  }

  async function deleteList(e, id) {
    e.stopPropagation();
    if (!confirm('¿Eliminar esta lista y todos sus productos?')) return;
    await sb.from('lists').delete().eq('id', id);
    lists = lists.filter(l => l.id !== id);
    if (activeList?.id === id) { activeList = null; renderMain(); }
    renderSidebar();
    toast('🗑️ Lista eliminada');
  }

  /* ── SELECT LIST ── */
  async function selectList(id) {
    activeList = lists.find(l => l.id === id);
    renderSidebar();
    renderMain(true);
    await loadItems();
    renderMain();
  }

  /* ── ITEMS ── */
  async function loadItems() {
    const { data } = await sb.from('items').select('*').eq('list_id', activeList.id).order('created_at');
    items = data || [];
    const l = lists.find(l => l.id === activeList.id);
    if (l) l._count = items.length;
    renderSidebar();
  }

  function renderMain(loading = false) {
    const main = document.getElementById('main');
    if (!activeList) {
      main.innerHTML = `<div class="main-empty"><div class="big">👈</div><p>Selecciona o crea una lista</p></div>`;
      return;
    }
    const checked = items.filter(i => i.checked).length;
    const total = items.length;
    const pct = total ? Math.round(checked / total * 100) : 0;
    main.innerHTML = `
      <div class="main-header">
        <h2>${esc(activeList.name)}</h2>
        ${total ? `<span class="progress-pill">${checked}/${total}</span>` : ''}
      </div>
      ${total ? `<div class="progress-bar-wrap"><div class="progress-bar" style="width:${pct}%"></div></div>` : ''}
      <div class="add-item-row">
        <div class="search-wrap">
          <input id="input-new-item" placeholder="Buscar en Mercadona o escribe libremente…" maxlength="80"
            oninput="onSearchInput(this.value)"
            onkeydown="onSearchKeyDown(event)" />
          <div class="dropdown" id="dropdown" style="display:none"></div>
        </div>
        <button onclick="addFreeText()">Añadir</button>
      </div>
      <div class="items-scroll" id="items-container">
        ${loading ? `<div style="text-align:center;padding:40px"><div class="loader"></div></div>` : renderItems()}
      </div>`;
    document.getElementById('input-new-item')?.focus();
    document.addEventListener('click', closeDropdownOutside);
  }

  function renderItems() {
    if (!items.length) return `<div class="items-empty"><div class="big">🧺</div><p>Aún no hay productos. ¡Busca o añade el primero!</p></div>`;
    const pending = items.filter(i => !i.checked);
    const done = items.filter(i => i.checked);
    let html = pending.map(itemHTML).join('');
    if (done.length) {
      html += `<p style="font-size:11px;text-transform:uppercase;letter-spacing:.08em;color:var(--muted);margin:16px 0 8px;font-weight:600;">Completados</p>`;
      html += done.map(itemHTML).join('');
    }
    return html;
  }

  function itemHTML(item) {
    const thumb = item.thumbnail
      ? `<img class="item-thumb" src="${item.thumbnail}" alt="" onerror="this.style.display='none'">`
      : `<div class="item-no-thumb">🛒</div>`;
    return `
      <div class="item-row ${item.checked ? 'checked' : ''}" onclick="toggleItem('${item.id}')">
        ${thumb}
        <div class="checkbox">${item.checked ? '✓' : ''}</div>
        <div class="item-info">
          <div class="item-name">${esc(item.name)}</div>
          ${item.price ? `<div class="item-price">${item.price}</div>` : ''}
        </div>
        <button class="del-item" onclick="deleteItem(event,'${item.id}')">✕</button>
      </div>`;
  }

  async function addItem(name, price = null, thumbnail = null) {
    if (!name || !activeList) return;
    const payload = { name, list_id: activeList.id, checked: false };
    if (price) payload.price = price;
    if (thumbnail) payload.thumbnail = thumbnail;
    const { data, error } = await sb.from('items').insert(payload).select().single();
    if (error) { toast('❌ ' + error.message); return; }
    items.push(data);
    const l = lists.find(l => l.id === activeList.id);
    if (l) l._count = items.length;
    renderSidebar();
    updateItemsUI();
    const inp = document.getElementById('input-new-item');
    if (inp) { inp.value = ''; inp.focus(); }
    closeDropdown();
  }

  function addFreeText() {
    const inp = document.getElementById('input-new-item');
    const name = inp?.value.trim();
    if (name) addItem(name);
  }

  async function toggleItem(id) {
    const item = items.find(i => i.id === id);
    if (!item) return;
    await sb.from('items').update({ checked: !item.checked }).eq('id', id);
    item.checked = !item.checked;
    updateItemsUI();
  }

  async function deleteItem(e, id) {
    e.stopPropagation();
    await sb.from('items').delete().eq('id', id);
    items = items.filter(i => i.id !== id);
    const l = lists.find(l => l.id === activeList.id);
    if (l) l._count = items.length;
    renderSidebar();
    updateItemsUI();
  }

  function updateItemsUI() {
    const checked = items.filter(i => i.checked).length;
    const total = items.length;
    const pct = total ? Math.round(checked / total * 100) : 0;
    const pill = document.querySelector('.progress-pill');
    const bar = document.querySelector('.progress-bar');
    if (pill) pill.textContent = `${checked}/${total}`;
    if (bar) bar.style.width = pct + '%';
    const c = document.getElementById('items-container');
    if (c) c.innerHTML = renderItems();
  }

  /* ── MERCADONA SEARCH ── */
  function onSearchInput(val) {
    clearTimeout(searchTimeout);
    if (!val.trim() || val.length < 2) { closeDropdown(); return; }
    showDropdownLoading();
    searchTimeout = setTimeout(() => searchMercadona(val.trim()), 400);
  }

  async function searchMercadona(q) {
    try {
      const res = await fetch(`/api/mercadona?q=${encodeURIComponent(q)}`);
      const data = await res.json();
      // Handle different response shapes
      const products = data.results || data.products || data.items || [];
      dropdownResults = products.slice(0, 8);
      dropdownIndex = -1;
      renderDropdown();
    } catch (e) {
      closeDropdown();
    }
  }

  function showDropdownLoading() {
    const dd = document.getElementById('dropdown');
    if (!dd) return;
    dd.style.display = 'block';
    dd.innerHTML = `<div class="dropdown-loading"><div class="loader" style="margin:0 auto"></div></div>`;
  }

  function renderDropdown() {
    const dd = document.getElementById('dropdown');
    if (!dd) return;
    if (!dropdownResults.length) {
      dd.style.display = 'block';
      dd.innerHTML = `<div class="dropdown-empty">Sin resultados en Mercadona — pulsa Añadir para añadirlo igual</div>`;
      return;
    }
    dd.style.display = 'block';
    dd.innerHTML = dropdownResults.map((p, i) => {
      const name = p.display_name || p.name || '—';
      const price = p.price_instructions?.unit_price ? `${p.price_instructions.unit_price} €` : '';
      const size = p.price_instructions?.size_format || '';
      const thumb = p.thumbnail || (p.photos && p.photos[0]?.thumbnail) || '';
      const img = thumb
        ? `<img src="${thumb}" alt="" onerror="this.style.display='none'">`
        : `<div class="no-img">🛒</div>`;
      return `
        <div class="dropdown-item ${i === dropdownIndex ? 'active' : ''}"
             onclick="selectProduct(${i})">
          ${img}
          <div class="prod-info">
            <div class="prod-name">${esc(name)}</div>
            ${size ? `<div class="prod-sub">${esc(size)}</div>` : ''}
          </div>
          ${price ? `<div class="prod-price">${price}</div>` : ''}
        </div>`;
    }).join('');
  }

  function selectProduct(i) {
    const p = dropdownResults[i];
    if (!p) return;
    const name = p.display_name || p.name;
    const price = p.price_instructions?.unit_price ? `${p.price_instructions.unit_price} €` : null;
    const thumb = p.thumbnail || (p.photos && p.photos[0]?.thumbnail) || null;
    addItem(name, price, thumb);
  }

  function onSearchKeyDown(e) {
    const dd = document.getElementById('dropdown');
    if (!dd || dd.style.display === 'none') {
      if (e.key === 'Enter') addFreeText();
      return;
    }
    if (e.key === 'ArrowDown') {
      e.preventDefault();
      dropdownIndex = Math.min(dropdownIndex + 1, dropdownResults.length - 1);
      renderDropdown();
    } else if (e.key === 'ArrowUp') {
      e.preventDefault();
      dropdownIndex = Math.max(dropdownIndex - 1, -1);
      renderDropdown();
    } else if (e.key === 'Enter') {
      e.preventDefault();
      if (dropdownIndex >= 0 && dropdownResults[dropdownIndex]) {
        selectProduct(dropdownIndex);
      } else {
        addFreeText();
      }
    } else if (e.key === 'Escape') {
      closeDropdown();
    }
  }

  function closeDropdown() {
    const dd = document.getElementById('dropdown');
    if (dd) dd.style.display = 'none';
    dropdownResults = [];
    dropdownIndex = -1;
  }

  function closeDropdownOutside(e) {
    if (!e.target.closest('.search-wrap')) closeDropdown();
  }

  /* ── HELPERS ── */
  function esc(s) {
    return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
  }

  document.getElementById('input-new-list').addEventListener('keydown', e => {
    if (e.key === 'Enter') createList();
  });

  loadLists();
</script>
</body>
</html>
