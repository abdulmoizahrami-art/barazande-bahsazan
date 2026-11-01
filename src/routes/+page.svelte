<script>
  import { brand, about, products, steps, pledge } from '#lib/data/site.js';
  import Hero from '#lib/components/Hero.svelte';
  import Section from '#lib/components/Section.svelte';
  import Card from '#lib/components/Card.svelte';
  import Steps from '#lib/components/Steps.svelte';
  import Pledge from '#lib/components/Pledge.svelte';
  import ContactInfo from '#lib/components/ContactInfo.svelte';
</script>

<svelte:head>
  <title>{brand.name} | {brand.type}</title>
  <meta name="description" content="برازنده شمال؛ شرکت تولید سفال‌سازی در شمال افغانستان. ظروف، خشت و کاشی دست‌ساز." />
</svelte:head>

<Hero />

<Section id="about" title="درباره ما">
  <div class="about">{#each about as p}<p>{p}</p>{/each}</div>
</Section>

<Section id="products" title="محصولات" alt>
  <ul class="cards">
    {#each products as p}<Card {...p} />{/each}
  </ul>
</Section>

<Section id="process" title="از گِل تا سفال"><Steps items={steps} /></Section>

<Section id="pledge" title="تعهد ما" alt><Pledge items={pledge} /></Section>

<Section id="contact" title="تماس با ما"><ContactInfo /></Section>

<style>
  .about p{max-width:62ch;color:var(--muted)}
  .about p + p{margin-top:14px}
  .cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:var(--space-3)}
</style>
