<template>
  <div>
    <nav
      class="navbar header has-shadow is-primary"
      role="navigation"
      aria-label="main navigation">
      <div class="navbar-brand">
        <a
          class="navbar-item"
          href="/">Rubocop Guide</a>

        <div class="navbar-burger">
          <span/>
          <span/>
          <span/>
        </div>
      </div>
    </nav>

    <section class="main-content columns">

      <aside class="column is-2 section">
        <ul class="menu-list">
          <li
            v-for="(item, key) of items"
            :key="key">
            <nuxt-link
              :to="item.to"
              exact-active-class="is-active">
              {{ item.title }}
            </nuxt-link>
          </li>
        </ul>
      </aside>

      <div class="container column is-10">
        <nuxt />
      </div>

    </section>

    <footer class="footer">
      <div class="content has-text-centered">
        <p>
          <img
            src="~assets/buefy.png"
            alt="Buefy"
            height="28"
            width="50">
          <strong>Bulma</strong> by <a href="https://jgthms.com">Jeremy Thomas</a>. The source code is licensed
          <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content
          is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: 'Bundler', to: { name: 'Bundler' } },
        { title: 'Correctors', to: { name: 'Correctors' } },
        { title: 'Gemspec', to: { name: 'Gemspec' } },
        { title: 'Generator', to: { name: 'Generator' } },
        { title: 'InternalAffairs', to: { name: 'InternalAffairs' } },
        { title: 'Layout', to: { name: 'Layout' } },
        { title: 'Lint', to: { name: 'Lint' } },
        { title: 'Metrics', to: { name: 'Metrics' } },
        { title: 'Mixin', to: { name: 'Mixin' } },
        { title: 'Naming', to: { name: 'Naming' } },
        { title: 'Performance', to: { name: 'Performance' } },
        { title: 'Rails', to: { name: 'Rails' } },
        { title: 'Security', to: { name: 'Security' } },
        { title: 'Style', to: { name: 'Style' } },
        { title: 'VariableForce', to: { name: 'VariableForce' } }
      ]
    }
  }
}
</script>
