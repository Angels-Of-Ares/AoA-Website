<script>
  import Markdown from '../components/blocks/Markdown.svelte'
  import lore from '../_contents/lore.md'
</script>


<style lang="scss">
  @import '../styles/mixins';
  @import '../styles/variables';
  .bg-wings {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: url(/images/wings-bg.jpg) no-repeat top center;
    background-size: cover;
    z-index: -1;
    animation: bg-appear 8s ease-out both 1s;

    @media (max-width: 768px) {
      background-size: contain;
      background-position: top center;
      background-repeat: no-repeat;
    }
  }

  .page-title {
    span {
      display: block;
      @include min-width($breakpoint-md) {
        display: inline;   
      }
    }
  }
  .content {
    position: relative;
    font-size: 1.1rem;
    line-height: 1.6;
    background: rgba(0, 0, 0, 0.6);
    padding: 2rem;
    border-radius: 8px;

    :global(.markdown) {
      columns: 1;

      :global(> *:last-child) {
        margin-bottom: 0;
      }
      :global(:first-child) {
        margin-top: 0;
      }
    }
  }

  .actions {
    margin-top: 2.5em;
    text-align: center;
    a {
      margin: 0.25em;
    }
  }

  :global(h1) {
    animation: text-appear 5s ease-out both 0s;
  }

  @mixin appear($name, $initial-scale) {
    @keyframes #{$name} {
      0% {
        transform: scale($initial-scale);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: scale(1);
        opacity: 1;
      }
    }
  }

  @include appear(bg-appear, 0.5);
  @include appear(text-appear, 0.875);
</style>

<svelte:head>
	<title>Lore - Angels of Ares</title>
</svelte:head>

<div class="container">
<div class="bg-wings"></div>
  <h1 class="page-title">
    <span>
      Lore
    </span>
  </h1>
  <div class="content">
    <Markdown content={lore} />
    <div class="actions">
    <a href="https://discord.gg/xykYJ8SEcN" target="_blank" class="primary-btn">
        Join The Angels
    </a>
    </div>
  </div>
</div>