<script>
  import { contact } from '#lib/data/site.js';
  import Button from './Button.svelte';
</script>

<dl>
  <dt>آدرس</dt><dd>{contact.address}</dd>
  <dt>تلفن</dt><dd class="ltr">{contact.phone}</dd>
  <dt>ایمیل</dt><dd class="ltr">{contact.email}</dd>
</dl>
<div class="cta"><Button href={contact.phoneLink}>زنگ بزنید</Button></div>

<style>
  dl{display:grid;grid-template-columns:120px 1fr;gap:10px 20px;margin-bottom:var(--space-4)}
  dt{color:var(--muted)}
  .ltr{direction:ltr;text-align:right}
  @media (max-width:760px){
    dl{grid-template-columns:1fr;gap:0}
    dd{margin-bottom:var(--space-2)}
    .cta :global(.btn){width:100%}
  }
</style>
