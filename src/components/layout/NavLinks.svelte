<script>
  import NavLink from '../elements/NavLink.svelte';
</script>


<style lang="scss">
  .nav {
    font-size: 1.25em;
  }
  .nav :global(a[href="#"]) {
    pointer-events: none;
    cursor: default;
  }
  .social {
    .subnav {
      white-space: nowrap;
    }
    .subitem {
      display: inline-block;

      i {
        font-size: 1.25em;
      }
    }
  }
</style>


<nav>
  <ul class="nav">

    <li class="item">
      <NavLink href="https://samurai.angelsofares.xyz" label="Samurai"/>
    </li>

    <li class="item">
      <NavLink href="/lore" label="Lore"/>
    </li>

    <li class="item social">
      <NavLink href="#" label="Join us!"/>
      <ul class="subnav">
        <li class="subitem">
          <NavLink href="https://discord.gg/xykYJ8SEcN" target="_blank">
            <i class="fab fa-discord"></i>
          </NavLink>
        </li>
        <li class="subitem">
          <NavLink href="https://twitter.com/TheAngelOfAres" target="_blank">
            <i class="fab fa-twitter"></i>
          </NavLink>
        </li>
      </ul>
    </li>
  </ul>
</nav>
