<script>
  import { brand } from '#lib/data/site.js';
</script>

<footer>
  <div class="container row">
    <span>© {brand.name} — تمام حقوق محفوظ است</span>
    <span>{brand.partner}</span>
  </div>
</footer>

<style>
  footer{padding-block:var(--space-4);color:var(--muted);font-size:14px}
  .row{display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px}
  @media (max-width:760px){.row{flex-direction:column}}
</style>
