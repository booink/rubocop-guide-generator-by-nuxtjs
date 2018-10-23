<template>
  <section class="section">
    <h2>Lint</h2>
    <section class="main-content columns">

      <aside class="column is-3 section">
        <ul class="menu-list">
          <li
            v-for="item of items"
            :key="item">
            <nuxt-link
              :to="`/Lint/${item}`"
              exact-active-class="is-active">
              {{ item }}
            </nuxt-link>
          </li>
        </ul>
      </aside>

      <div class="container column is-9">
        <nuxt-child/>
      </div>

    </section>
  </section>
</template>

<script>
export default {
  data() {
    return {
      items: ['UriEscapeUnescape']
    }
  }
}
</script>
