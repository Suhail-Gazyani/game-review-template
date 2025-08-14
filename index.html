<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Game Review Hub</title>
  <style>
    :root{--bg:#0f1724;--card:#0b1220;--accent:#06b6d4;--muted:#9aa6b2;--glass:rgba(255,255,255,0.03)}
    *{box-sizing:border-box;font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial}
    body{margin:0;background:linear-gradient(180deg,#071023 0%, #07182b 100%);color:#e6eef6;min-height:100vh;padding:24px}
    header{display:flex;gap:16px;align-items:center;justify-content:space-between}
    header h1{margin:0;font-size:20px;letter-spacing:0.4px}
    .container{max-width:1100px;margin:22px auto}
    .grid{display:grid;grid-template-columns:360px 1fr;gap:20px}

    /* Left panel - form */
    .card{background:var(--card);padding:18px;border-radius:12px;box-shadow:0 6px 20px rgba(2,6,23,0.6)}
    .card h2{margin:0 0 12px 0;font-size:16px}
    label{display:block;font-size:13px;color:var(--muted);margin:10px 0 6px}
    input[type=text],select,textarea{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:var(--glass);color:inherit}
    textarea{min-height:110px;resize:vertical}
    .row{display:flex;gap:8px}
    .btn{display:inline-block;padding:10px 14px;border-radius:10px;border:0;background:var(--accent);color:#022;cursor:pointer;margin-top:12px}
    .mutebtn{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted)}

    /* Reviews list */
    .toolbar{display:flex;gap:8px;align-items:center;flex-wrap:wrap;margin-bottom:12px}
    .search{flex:1}
    .reviews{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:14px}
    .review{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:12px;border-radius:10px;border:1px solid rgba(255,255,255,0.02)}
    .review .meta{display:flex;align-items:center;gap:10px}
    .thumb{width:64px;height:64px;border-radius:8px;background:#071826;flex-shrink:0;display:flex;align-items:center;justify-content:center;color:var(--muted);font-size:12px}
    .title{font-weight:600}
    .small{font-size:12px;color:var(--muted)}
    .stars{display:inline-block}
    .tag{display:inline-block;background:rgba(255,255,255,0.04);padding:6px 8px;border-radius:8px;font-size:12px;margin-right:6px}
    .actions{margin-top:8px;display:flex;gap:8px}
    .linklike{background:transparent;border:0;color:var(--accent);cursor:pointer}

    /* responsive */
    @media (max-width:880px){.grid{grid-template-columns:1fr}header{flex-direction:column;align-items:flex-start} .container{padding:0 8px}}

    footer{margin-top:20px;color:var(--muted);font-size:13px;text-align:center}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div>
        <h1>Game Review Hub</h1>
        <div class="small">Add, browse, search and sort game reviews. Data saved in your browser.</div>
      </div>
      <div>
        <button id="importBtn" class="mutebtn btn">Import sample</button>
        <button id="clearBtn" class="mutebtn btn">Clear all</button>
      </div>
    </header>

    <main class="grid" role="main">
      <section class="card" aria-labelledby="add-review">
        <h2 id="add-review">Add / Edit Review</h2>
        <input id="idField" type="hidden" />
        <label for="gameTitle">Game title</label>
        <input id="gameTitle" type="text" placeholder="E.g. Hollow Knight" />

        <label for="platform">Platform</label>
        <select id="platform">
          <option>PC</option>
          <option>PlayStation</option>
          <option>Xbox</option>
          <option>Nintendo Switch</option>
          <option>Mobile</option>
          <option>Other</option>
        </select>

        <label for="rating">Rating (1-5)</label>
        <select id="rating">
          <option value="5">★★★★★ 5</option>
          <option value="4">★★★★ 4</option>
          <option value="3">★★★ 3</option>
          <option value="2">★★ 2</option>
          <option value="1">★ 1</option>
        </select>

        <label for="tags">Tags (comma separated)</label>
        <input id="tags" type="text" placeholder="metroidvania, indie, singleplayer" />

        <label for="cover">Cover image URL (optional)</label>
        <input id="cover" type="text" placeholder="https://...jpg" />

        <label for="reviewText">Review text</label>
        <textarea id="reviewText" placeholder="What you liked, disliked, replayability..."></textarea>

        <div style="display:flex;gap:8px;align-items:center">
          <button id="saveBtn" class="btn">Save review</button>
          <button id="resetBtn" class="mutebtn btn">Reset</button>
        </div>

        <hr style="border:none;height:1px;background:rgba(255,255,255,0.03);margin:12px 0">
        <div class="small">Tip: click a review's "Edit" button to load it here for quick changes.</div>
      </section>

      <section>
        <div class="card" style="margin-bottom:12px">
          <div class="toolbar">
            <input id="search" class="search" type="text" placeholder="Search by title, platform or tags" />
            <select id="sort">
              <option value="newest">Newest</option>
              <option value="oldest">Oldest</option>
              <option value="rating-desc">Highest rating</option>
              <option value="rating-asc">Lowest rating</option>
            </select>
            <button id="exportBtn" class="mutebtn btn">Export JSON</button>
          </div>
          <div id="reviewsContainer" class="reviews" aria-live="polite"></div>
        </div>

        <footer>Built with ❤️ — localStorage only. Not sent anywhere.</footer>
      </section>
    </main>
  </div>

  <script>
    // Simple in-browser game review app. Data persisted to localStorage under key 'gameReviews_v1'
    const LS_KEY = 'gameReviews_v1';

    // UI refs
    const idField = document.getElementById('idField');
    const gameTitle = document.getElementById('gameTitle');
    const platform = document.getElementById('platform');
    const rating = document.getElementById('rating');
    const tags = document.getElementById('tags');
    const cover = document.getElementById('cover');
    const reviewText = document.getElementById('reviewText');
    const saveBtn = document.getElementById('saveBtn');
    const resetBtn = document.getElementById('resetBtn');
    const reviewsContainer = document.getElementById('reviewsContainer');
    const search = document.getElementById('search');
    const sort = document.getElementById('sort');
    const importBtn = document.getElementById('importBtn');
    const clearBtn = document.getElementById('clearBtn');
    const exportBtn = document.getElementById('exportBtn');

    // load
    let reviews = loadReviews();
    render();

    // event listeners
    saveBtn.addEventListener('click', onSave);
    resetBtn.addEventListener('click', resetForm);
    search.addEventListener('input', render);
    sort.addEventListener('change', render);
    importBtn.addEventListener('click', importSample);
    clearBtn.addEventListener('click', clearAll);
    exportBtn.addEventListener('click', exportJSON);

    function generateId(){return 'r_'+Math.random().toString(36).slice(2,9)}

    function loadReviews(){
      try{
        const raw = localStorage.getItem(LS_KEY);
        if(!raw) return [];
        return JSON.parse(raw);
      }catch(e){console.error('Failed to load reviews',e);return []}
    }

    function saveReviews(){
      localStorage.setItem(LS_KEY, JSON.stringify(reviews));
    }

    function onSave(){
      const title = gameTitle.value.trim();
      if(!title){alert('Please provide a game title');return}
      const obj = {
        id: idField.value || generateId(),
        title,
        platform: platform.value,
        rating: Number(rating.value),
        tags: tags.value.split(',').map(s=>s.trim()).filter(Boolean),
        cover: cover.value.trim(),
        text: reviewText.value.trim(),
        createdAt: idField.value ? (reviews.find(r=>r.id===idField.value)?.createdAt || Date.now()) : Date.now(),
        updatedAt: Date.now()
      };

      // insert or replace
      const idx = reviews.findIndex(r=>r.id===obj.id);
      if(idx>=0) reviews[idx] = obj; else reviews.unshift(obj);
      saveReviews();
      resetForm();
      render();
    }

    function resetForm(){
      idField.value='';gameTitle.value='';platform.value='PC';rating.value='5';tags.value='';cover.value='';reviewText.value='';
      saveBtn.textContent='Save review';
    }

    function render(){
      // filter and sort
      const q = search.value.trim().toLowerCase();
      let list = reviews.filter(r=>{
        if(!q) return true;
        return r.title.toLowerCase().includes(q) || r.platform.toLowerCase().includes(q) || r.tags.join(' ').toLowerCase().includes(q) || (r.text||'').toLowerCase().includes(q);
      });

      const s = sort.value;
      if(s==='newest') list.sort((a,b)=>b.createdAt - a.createdAt);
      if(s==='oldest') list.sort((a,b)=>a.createdAt - b.createdAt);
      if(s==='rating-desc') list.sort((a,b)=>b.rating - a.rating);
      if(s==='rating-asc') list.sort((a,b)=>a.rating - b.rating);

      reviewsContainer.innerHTML='';
      if(list.length===0){reviewsContainer.innerHTML='<div class="small">No reviews yet — add one on the left or import sample.</div>';return}

      for(const r of list){
        const div = document.createElement('div'); div.className='review';

        const meta = document.createElement('div'); meta.className='meta';
        const thumb = document.createElement('div'); thumb.className='thumb';
        if(r.cover){
          const img = document.createElement('img'); img.src = r.cover; img.alt = r.title; img.style.width='100%'; img.style.height='100%'; img.style.objectFit='cover'; img.style.borderRadius='8px';
          thumb.innerHTML=''; thumb.appendChild(img);
        } else {
          thumb.textContent = r.platform;
        }
        meta.appendChild(thumb);

        const m2 = document.createElement('div'); m2.style.flex='1';
        const t = document.createElement('div'); t.className='title'; t.textContent = r.title;
        const small = document.createElement('div'); small.className='small'; small.textContent = r.platform + ' • ' + (new Date(r.createdAt)).toLocaleDateString();
        const stars = document.createElement('div'); stars.className='stars'; stars.innerHTML = renderStars(r.rating);
        m2.appendChild(t); m2.appendChild(stars); m2.appendChild(small);

        meta.appendChild(m2);
        div.appendChild(meta);

        if(r.tags && r.tags.length) {
          const tagRow = document.createElement('div'); tagRow.style.marginTop='8px';
          r.tags.slice(0,5).forEach(tag=>{const sp=document.createElement('span');sp.className='tag';sp.textContent=tag;tagRow.appendChild(sp)});
          div.appendChild(tagRow);
        }

        if(r.text){const p=document.createElement('p');p.style.margin='8px 0 0 0';p.className='small';p.textContent = r.text;div.appendChild(p)}

        const actions = document.createElement('div'); actions.className='actions';
        const edit = document.createElement('button'); edit.className='linklike'; edit.textContent='Edit'; edit.addEventListener('click',()=>loadIntoForm(r.id));
        const del = document.createElement('button'); del.className='linklike'; del.textContent='Delete'; del.addEventListener('click',()=>deleteReview(r.id));
        actions.appendChild(edit); actions.appendChild(del);
        div.appendChild(actions);

        reviewsContainer.appendChild(div);
      }
    }

    function renderStars(n){
      let out=''; for(let i=0;i<5;i++) out += i<n ? '★' : '☆'; return '<span aria-hidden="true">'+out+'</span> <span class="small">('+n+')</span>';
    }

    function loadIntoForm(id){
      const r = reviews.find(x=>x.id===id); if(!r) return;
      idField.value = r.id; gameTitle.value = r.title; platform.value = r.platform; rating.value = r.rating; tags.value = r.tags.join(', '); cover.value = r.cover || ''; reviewText.value = r.text || '';
      saveBtn.textContent='Update review'; window.scrollTo({top:0,behavior:'smooth'});
    }

    function deleteReview(id){
      if(!confirm('Delete this review?')) return;
      reviews = reviews.filter(r=>r.id!==id); saveReviews(); render();
    }

    function importSample(){
      const sample = [
        {id:generateId(),title:'Hades',platform:'PC',rating:5,tags:['roguelike','action'],cover:'',text:'Fast-paced combat, excellent progression loop.',createdAt:Date.now()-1000*60*60*24*30,updatedAt:Date.now()-1000*60*60*24*30},
        {id:generateId(),title:'Celeste',platform:'Nintendo Switch',rating:5,tags:['platformer','indie'],cover:'',text:'Tight controls and a touching story.',createdAt:Date.now()-1000*60*60*24*60,updatedAt:Date.now()-1000*60*60*24*60},
        {id:generateId(),title:'FIFA 24',platform:'PlayStation',rating:3,tags:['sports','multiplayer'],cover:'',text:'Solid, but microtransaction push is strong.',createdAt:Date.now()-1000*60*60*24*10,updatedAt:Date.now()-1000*60*60*24*10}
      ];
      // merge but avoid duplicates by title
      for(const s of sample){ if(!reviews.some(r=>r.title.toLowerCase()===s.title.toLowerCase())) reviews.push(s) }
      saveReviews(); render();
    }

    function clearAll(){ if(!confirm('Clear all reviews? This cannot be undone.')) return; reviews=[]; saveReviews(); render(); }

    function exportJSON(){ const blob = new Blob([JSON.stringify(reviews, null, 2)], {type:'application/json'}); const url = URL.createObjectURL(blob); const a = document.createElement('a'); a.href = url; a.download = 'game-reviews.json'; a.click(); URL.revokeObjectURL(url); }

    // keyboard: ctrl+enter to save
    document.addEventListener('keydown', (e)=>{ if((e.ctrlKey||e.metaKey) && e.key==='Enter'){ onSave(); } });

    // accessibility: announce load
    reviewsContainer.setAttribute('role','list');
  </script>
</body>
</html>
