<script>
  let { items } = $props();
</script>

<ol>
  {#each items as s}
    <li><div><h3>{s.title}</h3><p>{s.text}</p></div></li>
  {/each}
</ol>

<style>
  ol{counter-reset:s}
  li{counter-increment:s;display:grid;grid-template-columns:64px 1fr;gap:var(--space-3);padding-block:22px;border-top:1px solid var(--line)}
  li:last-child{border-bottom:1px solid var(--line)}
  li::before{content:counter(s,persian);font-size:34px;font-weight:800;color:var(--gold-text);line-height:1.2}
  h3{font-size:21px}
  p{color:var(--muted)}
  @media (max-width:760px){li{grid-template-columns:44px 1fr;gap:var(--space-2)}}
</style>
