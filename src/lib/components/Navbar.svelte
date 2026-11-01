<script>
  import { brand, nav } from '#lib/data/site.js';

  let open = $state(false);   // منوی موبایل باز است؟
  let active = $state('');    // بخشی که الان در صفحه دیده می‌شود

  // لینک فعال: هر بخشی که وسط صفحه برسد
  $effect(() => {
    const io = new IntersectionObserver(
      (entries) => { for (const e of entries) if (e.isIntersecting) active = e.target.id; },
      { rootMargin: '-45% 0px -50% 0px' }
    );
    for (const l of nav) { const el = document.getElementById(l.id); if (el) io.observe(el); }
    return () => io.disconnect();
  });
</script>

<svelte:window onkeydown={(e) => e.key === 'Escape' && (open = false)} />

<header class="nav">
  <div class="container bar">
    <a class="brand" href="#top"><img src="/logo.png" alt="" width="42" height="40" /><span>{brand.name}</span></a>

    <button class="toggle" type="button" aria-controls="menu" aria-expanded={open}
      aria-label={open ? 'بستن منو' : 'باز کردن منو'} onclick={() => (open = !open)}><span></span></button>

    <nav id="menu" class="links" class:is-open={open} aria-label="منوی اصلی">
      {#each nav as l}
        <a href="#{l.id}" aria-current={active === l.id ? 'true' : undefined} onclick={() => (open = false)}>{l.label}</a>
      {/each}
    </nav>
  </div>
</header>

<style>
  .nav{position:sticky;top:0;z-index:10;background:var(--nav-bg);backdrop-filter:blur(8px);border-bottom:1px solid var(--line);padding-top:env(safe-area-inset-top,0px)}
  .bar{display:flex;flex-wrap:wrap;align-items:center;justify-content:space-between;gap:var(--space-2);min-height:64px}
  .brand{display:flex;align-items:center;gap:12px;text-decoration:none;font-weight:800;color:var(--gold-text)}
  .brand img{width:42px;height:auto}
  .links{display:flex;gap:var(--space-3);font-size:15px}
  .links a{text-decoration:none;color:var(--muted);padding-block:6px}
  .links a:hover,.links a:focus-visible,.links a[aria-current]{color:var(--gold-text)}
  .links a[aria-current]{box-shadow:0 2px 0 var(--gold)}

  .toggle{display:none;width:48px;height:48px;position:relative;background:none;border:1px solid var(--line);border-radius:var(--radius);color:var(--gold-text);cursor:pointer}
  .toggle span,.toggle span::before,.toggle span::after{position:absolute;height:2px;background:currentColor;content:"";transition:transform .25s,background .2s}
  .toggle span{top:22px;inset-inline:13px}
  .toggle span::before{top:-7px;inset-inline:0}
  .toggle span::after{top:7px;inset-inline:0}
  .toggle[aria-expanded="true"] span{background:transparent}
  .toggle[aria-expanded="true"] span::before{transform:translateY(7px) rotate(45deg)}
  .toggle[aria-expanded="true"] span::after{transform:translateY(-7px) rotate(-45deg)}

  @media (max-width:860px){
    .toggle{display:block}
    .links{display:none;flex:1 0 100%;flex-direction:column;gap:0;padding-bottom:var(--space-2);font-size:17px}
    .links.is-open{display:flex}
    .links a{display:flex;align-items:center;min-height:48px;border-top:1px solid var(--line);box-shadow:none!important}
  }
</style>
