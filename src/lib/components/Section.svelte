<script>
  let { id, title, alt = false, children } = $props();
</script>

<section {id} class="section" class:alt>
  <div class="container">
    <h2>{title}</h2>
    {@render children()}
  </div>
</section>

<style>
  .section{padding-block:clamp(48px,9vw,88px);border-bottom:1px solid var(--line)}
  .alt{background:var(--bg-alt)}
  h2{font-size:var(--fs-h2);font-weight:800;margin-bottom:var(--space-4)}
  h2::after{content:"";display:block;width:48px;height:3px;background:var(--gold);margin-top:var(--space-1)}
</style>
