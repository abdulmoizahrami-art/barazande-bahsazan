<script>
  let { title, text, icon } = $props();
</script>

<li class="card">
  <svg viewBox="0 0 48 48" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linejoin="round" aria-hidden="true">
    <path d={icon} />
  </svg>
  <h3>{title}</h3>
  <p>{text}</p>
</li>

<style>
  .card{padding:var(--space-3);border:1px solid var(--line);border-radius:var(--radius);background:var(--bg-alt);transition:transform .25s,border-color .25s}
  .card:hover{transform:translateY(-4px);border-color:var(--gold)}
  svg{width:44px;height:44px;color:var(--gold-text);margin-bottom:var(--space-2)}
  h3{font-size:21px;color:var(--gold-text)}
  p{color:var(--muted);margin-top:6px}
  @media (prefers-reduced-motion:reduce){.card{transition:none}}
</style>
