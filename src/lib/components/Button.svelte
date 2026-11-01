<script>
  let { href, variant = 'solid', children } = $props();
</script>

<a {href} class="btn {variant}">{@render children()}</a>

<style>
  .btn{display:inline-flex;align-items:center;justify-content:center;min-height:48px;padding:12px 28px;
    border-radius:var(--radius);font-weight:600;text-decoration:none;
    background:var(--gold);color:var(--on-gold);border:1px solid var(--gold);transition:filter .2s}
  .btn:hover{filter:brightness(1.1)}
  .ghost{background:none;color:var(--gold-text)}
</style>
