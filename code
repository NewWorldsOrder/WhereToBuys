<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Buy List — A Field Catalog</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#12203a;
    --paper:#f2ede1;
    --card:#faf7ef;
    --amber:#e0a52c;
    --rust:#b8452f;
    --line: rgba(18,32,58,0.14);
    --line-strong: rgba(18,32,58,0.28);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--ink);
    color:var(--paper);
    font-family:'IBM Plex Sans', sans-serif;
    -webkit-font-smoothing:antialiased;
  }
  a{color:inherit;}

  /* ===== HERO ===== */
  .hero{
    position:relative;
    padding:5.5rem 6vw 4rem;
    background:
      radial-gradient(circle at 85% 15%, rgba(224,165,44,0.16), transparent 45%),
      var(--ink);
    border-bottom:1px solid rgba(242,237,225,0.15);
    overflow:hidden;
  }
  .hero .kicker{
    font-family:'IBM Plex Mono', monospace;
    letter-spacing:0.28em;
    text-transform:uppercase;
    font-size:0.72rem;
    color:var(--amber);
    display:flex;
    align-items:center;
    gap:0.7rem;
  }
  .hero .kicker::before{
    content:"";
    width:26px; height:1px;
    background:var(--amber);
    display:inline-block;
  }
  .hero h1{
    font-family:'Oswald', sans-serif;
    font-weight:700;
    text-transform:uppercase;
    font-size:clamp(2.6rem, 7vw, 5.4rem);
    line-height:0.96;
    margin:0.9rem 0 0;
    letter-spacing:0.01em;
  }
  .hero h1 span{color:var(--amber);}
  .hero p.sub{
    max-width:46ch;
    margin:1.4rem 0 0;
    color:rgba(242,237,225,0.72);
    font-size:1.05rem;
    line-height:1.55;
  }
  .stamp{
    position:absolute;
    top:3.2rem; right:6vw;
    width:118px; height:118px;
    border:2px solid var(--rust);
    border-radius:50%;
    display:flex; align-items:center; justify-content:center;
    text-align:center;
    transform:rotate(-11deg);
    color:var(--rust);
    font-family:'IBM Plex Mono', monospace;
    font-size:0.62rem;
    letter-spacing:0.08em;
    text-transform:uppercase;
    line-height:1.35;
    opacity:0.85;
  }
  .stamp b{display:block; font-size:1.35rem; font-family:'Oswald',sans-serif; letter-spacing:0.03em;}

  /* ===== SEARCH BAR ===== */
  .toolbar{
    position:sticky; top:0; z-index:20;
    background:rgba(18,32,58,0.92);
    backdrop-filter:blur(8px);
    border-bottom:1px solid rgba(242,237,225,0.15);
    padding:0.9rem 6vw;
    display:flex; align-items:center; gap:1rem; flex-wrap:wrap;
  }
  .toolbar input{
    flex:1; min-width:220px;
    background:transparent;
    border:1px solid rgba(242,237,225,0.3);
    color:var(--paper);
    padding:0.6rem 0.9rem;
    font-family:'IBM Plex Mono', monospace;
    font-size:0.85rem;
    border-radius:2px;
  }
  .toolbar input::placeholder{color:rgba(242,237,225,0.45);}
  .toolbar input:focus{outline:none; border-color:var(--amber);}
  .toolbar .count{
    font-family:'IBM Plex Mono', monospace;
    font-size:0.75rem;
    color:rgba(242,237,225,0.55);
    white-space:nowrap;
  }

  /* ===== INDEX NAV ===== */
  .index-nav{
    padding:2.2rem 6vw 0.5rem;
    display:flex; flex-wrap:wrap; gap:0.5rem 0.7rem;
  }
  .index-nav a{
    font-family:'IBM Plex Mono', monospace;
    font-size:0.72rem;
    letter-spacing:0.04em;
    text-decoration:none;
    color:rgba(242,237,225,0.6);
    border:1px solid rgba(242,237,225,0.22);
    padding:0.32rem 0.7rem;
    border-radius:20px;
    transition:all .15s ease;
  }
  .index-nav a:hover{border-color:var(--amber); color:var(--amber);}

  /* ===== CATALOG ===== */
  .catalog{
    padding:2.5rem 6vw 6rem;
    display:flex; flex-direction:column;
  }
  .entry{
    padding:2.6rem 0;
    border-bottom:1px solid rgba(242,237,225,0.14);
    display:grid;
    grid-template-columns:220px 1fr;
    gap:2.2rem;
  }
  .entry:first-child{padding-top:0.5rem;}
  .entry.hidden{display:none;}

  .entry-head{display:flex; flex-direction:column; gap:0.6rem;}
  .entry-no{
    font-family:'IBM Plex Mono', monospace;
    color:var(--amber);
    font-size:0.78rem;
    letter-spacing:0.06em;
  }
  .entry-icon{font-size:2.4rem; line-height:1;}
  .entry-head h2{
    font-family:'Oswald', sans-serif;
    text-transform:uppercase;
    font-size:1.5rem;
    margin:0.1rem 0 0;
    letter-spacing:0.01em;
  }
  .entry-head p{
    margin:0;
    font-size:0.86rem;
    color:rgba(242,237,225,0.6);
    line-height:1.5;
    max-width:22ch;
  }

  .stores{
    display:grid;
    grid-template-columns:repeat(auto-fill, minmax(230px,1fr));
    gap:0.9rem;
  }
  .store-card{
    background:var(--card);
    color:var(--ink);
    border-radius:4px;
    padding:1.1rem 1.15rem 1rem;
    text-decoration:none;
    display:flex;
    flex-direction:column;
    gap:0.55rem;
    border:1px solid transparent;
    transition:transform .16s ease, border-color .16s ease, box-shadow .16s ease;
    position:relative;
    overflow:hidden;
  }
  .store-card:hover{
    transform:translateY(-3px);
    border-color:var(--rust);
    box-shadow:0 10px 24px rgba(0,0,0,0.28);
  }
  .store-top{display:flex; align-items:center; gap:0.6rem;}
  .badge{
    width:34px; height:34px;
    border-radius:50%;
    background:var(--ink);
    color:var(--amber);
    font-family:'Oswald',sans-serif;
    font-weight:600;
    font-size:0.85rem;
    display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
  }
  .store-name{
    font-family:'Oswald', sans-serif;
    font-size:1.02rem;
    text-transform:uppercase;
    letter-spacing:0.01em;
  }
  .store-note{
    font-size:0.82rem;
    color:rgba(18,32,58,0.68);
    line-height:1.4;
    flex-grow:1;
  }
  .store-cta{
    font-family:'IBM Plex Mono', monospace;
    font-size:0.7rem;
    letter-spacing:0.06em;
    text-transform:uppercase;
    color:var(--rust);
    display:flex; align-items:center; gap:0.35rem;
  }
  .store-card:hover .store-cta{gap:0.55rem;}
  .store-cta svg{width:11px; height:11px; transition:transform .16s ease;}

  footer{
    padding:2.5rem 6vw 3.5rem;
    border-top:1px solid rgba(242,237,225,0.15);
    font-family:'IBM Plex Mono', monospace;
    font-size:0.72rem;
    color:rgba(242,237,225,0.5);
    display:flex; justify-content:space-between; flex-wrap:wrap; gap:0.6rem;
  }

  @media (max-width:760px){
    .entry{grid-template-columns:1fr; gap:1rem;}
    .stamp{display:none;}
    .hero{padding:3.6rem 6vw 2.6rem;}
  }
</style>
</head>
<body>

<div class="hero">
  <div class="stamp"><b>15</b>CATEGORIES<br>VERIFIED<br>STORES</div>
  <div class="kicker">Field Catalog — Vol. 1</div>
  <h1>The Buy<br>List<span>.</span></h1>
  <p class="sub">No reviews to scroll through, no ranked "top 10" filler. Just the stores worth knowing for fifteen everyday categories — each one linked and ready.</p>
</div>

<div class="toolbar">
  <input id="filterInput" type="text" placeholder="Jump to a category — try 'pens' or 'coffee'…" oninput="filterCatalog()">
  <div class="count" id="resultCount">15 categories · 60 stores</div>
</div>

<nav class="index-nav" id="indexNav"></nav>

<div class="catalog" id="catalog"></div>

<footer>
  <span>THE BUY LIST — FIELD CATALOG VOL. 1</span>
  <span>LINKS GO TO OFFICIAL / MAJOR RETAIL SITES · NOT SPONSORED</span>
</footer>

<script>
const DATA = [
  {icon:"✒️", name:"Pens", note:"Fountain, gel, everyday carry.", stores:[
    {n:"JetPen", i:"JP", note:"The deepest fountain & gel pen catalog online, curated by pen nerds.", url:"https://www.jetpen.com"},
    {n:"Goulet Pens", i:"GP", note:"Fountain-pen specialists with excellent buying guides and swab videos.", url:"https://www.gouletpens.com"},
    {n:"Cult Pens", i:"CP", note:"UK-based, huge range from budget to luxury writing instruments.", url:"https://www.cultpens.com"},
    {n:"Amazon", i:"AZ", note:"Fastest option for known brands — Pilot, Uni-ball, Pentel, Muji.", url:"https://www.amazon.com/s?k=pens"}
  ]},
  {icon:"📓", name:"Notebooks", note:"Dot-grid, leather, refillable.", stores:[
    {n:"Baron Fig", i:"BF", note:"Design-forward dot-grid notebooks, cult favorite among planners.", url:"https://www.baronfig.com"},
    {n:"Moleskine", i:"MK", note:"The classic — hardcover, wide format range, widely stocked.", url:"https://www.moleskine.com"},
    {n:"Muji", i:"MJ", note:"Minimalist, affordable, great paper quality for the price.", url:"https://www.muji.com"},
    {n:"Amazon", i:"AZ", note:"Broadest selection, fast delivery, easy returns.", url:"https://www.amazon.com/s?k=notebooks"}
  ]},
  {icon:"☕", name:"Coffee", note:"Beans, subscriptions, gear.", stores:[
    {n:"Trade Coffee", i:"TC", note:"Matches you to roasters nationwide based on taste quiz.", url:"https://www.drinktrade.com"},
    {n:"Blue Bottle", i:"BB", note:"Own-roasted, consistent quality, strong subscription plans.", url:"https://bluebottlecoffee.com"},
    {n:"Peet's Coffee", i:"PC", note:"Dark-roast specialists, long-running mail order program.", url:"https://www.peets.com"},
    {n:"Amazon", i:"AZ", note:"Good for bulk restocks of a bean you already know.", url:"https://www.amazon.com/s?k=coffee+beans"}
  ]},
  {icon:"🎧", name:"Headphones", note:"Over-ear, IEMs, ANC.", stores:[
    {n:"B&H Photo", i:"BH", note:"Detailed specs, no sales tax in many states, trusted for audio gear.", url:"https://www.bhphotovideo.com"},
    {n:"Best Buy", i:"BB", note:"In-store demo before you buy, solid price-match policy.", url:"https://www.bestbuy.com"},
    {n:"Sony Store", i:"SO", note:"Direct from Sony for WH-1000X series and official warranty.", url:"https://electronics.sony.com"},
    {n:"Amazon", i:"AZ", note:"Widest brand range with easy A/B ordering and returns.", url:"https://www.amazon.com/s?k=headphones"}
  ]},
  {icon:"🎒", name:"Backpacks", note:"Travel, EDC, technical.", stores:[
    {n:"REI Co-op", i:"REI", note:"Hands-on testing culture, generous return policy on gear.", url:"https://www.rei.com"},
    {n:"Peak Design", i:"PD", note:"Camera & travel packs engineered by working photographers.", url:"https://www.peakdesign.com"},
    {n:"Fjällräven", i:"FJ", note:"Durable Scandinavian classics like the Kånken and Räven.", url:"https://www.fjallraven.com"},
    {n:"Amazon", i:"AZ", note:"Broadest budget-to-premium range in one place.", url:"https://www.amazon.com/s?k=backpacks"}
  ]},
  {icon:"👟", name:"Sneakers", note:"Retail, resale, rare drops.", stores:[
    {n:"Nike", i:"NK", note:"First-party access to SNKRS drops and full size runs.", url:"https://www.nike.com"},
    {n:"Foot Locker", i:"FL", note:"Multi-brand retailer with frequent restocks and in-store pickup.", url:"https://www.footlocker.com"},
    {n:"StockX", i:"SX", note:"Bid/ask marketplace for limited and sold-out releases.", url:"https://stockx.com"},
    {n:"Zappos", i:"ZP", note:"Free two-way shipping, deep size range, easy exchanges.", url:"https://www.zappos.com"}
  ]},
  {icon:"🪑", name:"Office Chairs", note:"Ergonomic, standing-desk adjacent.", stores:[
    {n:"Herman Miller", i:"HM", note:"The Aeron and Embody — the benchmark ergonomic chairs.", url:"https://www.hermanmiller.com"},
    {n:"Steelcase", i:"SC", note:"Enterprise-grade ergonomics, the Leap and Gesture lines.", url:"https://www.steelcase.com"},
    {n:"Wayfair", i:"WF", note:"Wide budget range with real customer photos and reviews.", url:"https://www.wayfair.com"},
    {n:"Amazon", i:"AZ", note:"Fast delivery and easy returns on mid-range chairs.", url:"https://www.amazon.com/s?k=office+chair"}
  ]},
  {icon:"🖥️", name:"Monitors", note:"4K, ultrawide, OLED.", stores:[
    {n:"B&H Photo", i:"BH", note:"Deep spec sheets, great for color-critical and creative work.", url:"https://www.bhphotovideo.com"},
    {n:"Dell", i:"DL", note:"Direct pricing on UltraSharp line with solid warranty support.", url:"https://www.dell.com"},
    {n:"Best Buy", i:"BB", note:"See panels in person before buying, price-match available.", url:"https://www.bestbuy.com"},
    {n:"Amazon", i:"AZ", note:"Broadest brand comparison in one checkout.", url:"https://www.amazon.com/s?k=monitor"}
  ]},
  {icon:"⌨️", name:"Mechanical Keyboards", note:"Switches, hot-swap, custom builds.", stores:[
    {n:"Keychron", i:"KC", note:"Hot-swappable boards with strong price-to-feature ratio.", url:"https://www.keychron.com"},
    {n:"Drop", i:"DR", note:"Enthusiast community drops — keycaps, switches, group buys.", url:"https://drop.com"},
    {n:"Das Keyboard", i:"DK", note:"Office-friendly mechanical boards, quieter switch options.", url:"https://www.daskeyboard.com"},
    {n:"Amazon", i:"AZ", note:"Fastest way to compare mainstream mechanical boards.", url:"https://www.amazon.com/s?k=mechanical+keyboard"}
  ]},
  {icon:"🖱️", name:"Wireless Mice", note:"Productivity & gaming.", stores:[
    {n:"Logitech", i:"LG", note:"Direct from the maker of the MX Master and G-series lines.", url:"https://www.logitech.com"},
    {n:"Best Buy", i:"BB", note:"In-hand testing before committing to a shape and weight.", url:"https://www.bestbuy.com"},
    {n:"B&H Photo", i:"BH", note:"Good for gaming-focused and niche ergonomic models.", url:"https://www.bhphotovideo.com"},
    {n:"Amazon", i:"AZ", note:"Fast restocks and easy comparisons across brands.", url:"https://www.amazon.com/s?k=wireless+mouse"}
  ]},
  {icon:"⌚", name:"Watches", note:"New, pre-owned, vintage.", stores:[
    {n:"Jomashop", i:"JM", note:"Discounted authorized dealer pricing on major watch brands.", url:"https://www.jomashop.com"},
    {n:"WatchBox", i:"WB", note:"Certified pre-owned luxury watches with warranty backing.", url:"https://www.thewatchbox.com"},
    {n:"Crown & Caliber", i:"CC", note:"Vetted pre-owned marketplace, transparent condition grading.", url:"https://www.crownandcaliber.com"},
    {n:"Amazon", i:"AZ", note:"Reliable for mainstream fashion and sport watch brands.", url:"https://www.amazon.com/s?k=watches"}
  ]},
  {icon:"🕶️", name:"Sunglasses", note:"Prescription-ready, polarized.", stores:[
    {n:"Warby Parker", i:"WP", note:"Home try-on program, prescription lenses built in.", url:"https://www.warbyparker.com"},
    {n:"Sunglass Hut", i:"SH", note:"Largest in-person and online selection of major brands.", url:"https://www.sunglasshut.com"},
    {n:"Ray-Ban", i:"RB", note:"Direct from the brand, full customization options.", url:"https://www.ray-ban.com"},
    {n:"Amazon", i:"AZ", note:"Fast comparison shopping across price tiers.", url:"https://www.amazon.com/s?k=sunglasses"}
  ]},
  {icon:"💧", name:"Water Bottles", note:"Insulated, filtered, everyday.", stores:[
    {n:"Hydro Flask", i:"HF", note:"Direct-from-brand color range and lid customization.", url:"https://www.hydroflask.com"},
    {n:"YETI", i:"YT", note:"Heavy-duty insulation built for outdoor and work use.", url:"https://www.yeti.com"},
    {n:"REI Co-op", i:"REI", note:"Curated outdoor-tested selection with knowledgeable staff.", url:"https://www.rei.com"},
    {n:"Amazon", i:"AZ", note:"Broadest budget range and fastest delivery.", url:"https://www.amazon.com/s?k=water+bottle"}
  ]},
  {icon:"🎲", name:"Board Games", note:"Family, strategy, party.", stores:[
    {n:"Miniature Market", i:"MM", note:"Deep strategy-game catalog with frequent sales.", url:"https://www.miniaturemarket.com"},
    {n:"Cool Stuff Inc", i:"CS", note:"Board games and TCGs with active community reviews.", url:"https://www.coolstuffinc.com"},
    {n:"Target", i:"TG", note:"Great for mainstream family and party games, easy returns.", url:"https://www.target.com"},
    {n:"Amazon", i:"AZ", note:"Fastest option for well-known titles and expansions.", url:"https://www.amazon.com/s?k=board+games"}
  ]},
  {icon:"🔪", name:"Kitchen Knives", note:"Chef's, Japanese, whetstones.", stores:[
    {n:"Williams Sonoma", i:"WS", note:"Curated premium brands with knife-skills guidance in store.", url:"https://www.williams-sonoma.com"},
    {n:"Sur La Table", i:"SL", note:"Strong Japanese knife selection, in-store sharpening classes.", url:"https://www.surlatable.com"},
    {n:"Crate & Barrel", i:"CB", note:"Reliable mid-range sets with cohesive block designs.", url:"https://www.crateandbarrel.com"},
    {n:"Amazon", i:"AZ", note:"Best for restocking a specific known blade or brand.", url:"https://www.amazon.com/s?k=kitchen+knives"}
  ]}
];

const arrowSvg = '<svg viewBox="0 0 12 12" fill="none"><path d="M2 10L10 2M10 2H4M10 2V8" stroke="currentColor" stroke-width="1.4"/></svg>';

function buildCatalog(){
  const catalog = document.getElementById('catalog');
  const nav = document.getElementById('indexNav');
  DATA.forEach((cat, idx) => {
    const no = String(idx+1).padStart(2,'0');

    const navLink = document.createElement('a');
    navLink.href = '#cat-'+idx;
    navLink.textContent = cat.name;
    nav.appendChild(navLink);

    const entry = document.createElement('div');
    entry.className = 'entry';
    entry.id = 'cat-'+idx;
    entry.dataset.name = cat.name.toLowerCase();

    const storesHtml = cat.stores.map(s => `
      <a class="store-card" href="${s.url}" target="_blank" rel="noopener noreferrer">
        <div class="store-top">
          <div class="badge">${s.i}</div>
          <div class="store-name">${s.n}</div>
        </div>
        <div class="store-note">${s.note}</div>
        <div class="store-cta">Visit store ${arrowSvg}</div>
      </a>
    `).join('');

    entry.innerHTML = `
      <div class="entry-head">
        <div class="entry-no">NO. ${no}</div>
        <div class="entry-icon">${cat.icon}</div>
        <h2>${cat.name}</h2>
        <p>${cat.note}</p>
      </div>
      <div class="stores">${storesHtml}</div>
    `;
    catalog.appendChild(entry);
  });
}

function filterCatalog(){
  const q = document.getElementById('filterInput').value.trim().toLowerCase();
  const entries = document.querySelectorAll('.entry');
  let visible = 0, storeCount = 0;
  entries.forEach(e => {
    const match = e.dataset.name.includes(q);
    e.classList.toggle('hidden', !match);
    if(match){ visible++; storeCount += e.querySelectorAll('.store-card').length; }
  });
  document.getElementById('resultCount').textContent = q
    ? `${visible} match${visible!==1?'es':''} · ${storeCount} stores`
    : `${DATA.length} categories · ${DATA.reduce((a,c)=>a+c.stores.length,0)} stores`;
}

buildCatalog();
</script>
</body>
</html>
