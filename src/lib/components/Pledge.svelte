<script>
  let { items } = $props();
</script>

<div class="pledge">
  {#each items as t}<p>{t}</p>{/each}
</div>

<style>
  .pledge{display:grid;grid-template-columns:1fr 1fr;border:1px solid var(--line);border-radius:var(--radius)}
  p{padding:34px 28px;font-size:clamp(19px,3vw,23px);font-weight:600;line-height:1.7}
  p + p{border-inline-start:1px solid var(--line)}
  @media (max-width:760px){
    .pledge{grid-template-columns:1fr}
    p{padding:24px 20px}
    p + p{border-inline-start:0;border-top:1px solid var(--line)}
  }
</style>
