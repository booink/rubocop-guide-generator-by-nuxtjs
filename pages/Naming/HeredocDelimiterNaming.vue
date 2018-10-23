<template>
  <section class="section">
    <h3>HeredocDelimiterNaming</h3>
    <ul>
      <li><a href="#overview">概要</a></li>
      <li><a href="#example">例</a></li>
      <li><a href="#why">なぜ？</a></li>
      <li><a href="#avoidance">回避する方法</a></li>
    </ul>
    <section
      id="overview"
      class="section">
      <h4>概要</h4>
      <blockquote cite="https://www.rubydoc.info/gems/rubocop/RuboCop/Cop/Naming/HeredocDelimiterNaming">
        This cop checks that your heredocs are using meaningful delimiters. By default it disallows `END` and `EO*`, and can be configured through blacklisting additional delimiters.
      </blockquote>
    </section>
    <section
      id="example"
      class="section">
      <h4>例</h4>
    </section>

    <section
      id="why"
      class="section">
      <h4>なぜ？</h4>
      <p>
        クラス名、メソッド名、変数名にも同様のことが言えると思いますが、ヒアドキュメント指定子にも何が値として設定されているかを、見た人が理解しやすい命名をするべき、と言う理念になっていると思われます。
      </p>
    </section>

    <section
      id="avoidance"
      class="section">
      <h4>回避する方法</h4>
      <h5>記述箇所のみ</h5>

      <h5>特定のメソッドのみ</h5>

      <h5>アプリケーション全体</h5>
    </section>
  </section>
</template>

<script>
export default {}
</script>
