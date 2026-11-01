<script>
  import { brand } from '#lib/data/site.js';
  import Button from './Button.svelte';
</script>

<section id="top" class="hero">
  <div class="container grid">
    <div>
      <h1>{brand.name}</h1>
      <p class="sub">{brand.type}</p>
      <p class="slogan">{brand.slogan}</p>
      <div class="actions">
        <Button href="#contact">تماس بگیرید</Button>
        <Button href="#products" variant="ghost">محصولات ما</Button>
      </div>
    </div>
    <img src="/logo.png" alt="لوگوی برازنده شمال: کوره سفال، خشت و دو دست" width="380" height="365" />
  </div>
</section>

<style>
  .hero{background:radial-gradient(circle at 25% 50%,rgba(201,162,74,.14),transparent 55%),var(--bg);border-bottom:1px solid var(--line)}
  .grid{display:grid;grid-template-columns:1.2fr 1fr;gap:var(--space-4);align-items:center;padding-block:clamp(48px,9vw,88px)}
  h1{font-size:var(--fs-h1);line-height:1.2;font-weight:800;color:var(--gold-text)}
  .sub{font-size:clamp(17px,2.4vw,20px);font-weight:300;margin:6px 0 var(--space-2)}
  .slogan{font-size:clamp(19px,3vw,24px);font-weight:600;border-inline-start:3px solid var(--gold);padding-inline-start:14px;margin-bottom:var(--space-4)}
  .actions{display:flex;flex-wrap:wrap;gap:12px}
  img{width:100%;max-width:380px;justify-self:center}
  @media (max-width:1000px){img{max-width:300px}}
  @media (max-width:760px){
    .grid{grid-template-columns:1fr;text-align:center;padding-block:var(--space-4)}
    img{order:-1;max-width:200px}
    .slogan{border:0;padding:0}
    .actions{flex-direction:column}
  }
  @media (prefers-reduced-motion:no-preference){
    img{animation:in .9s ease both}
    @keyframes in{from{opacity:0;transform:scale(.94)}}
  }
</style>
