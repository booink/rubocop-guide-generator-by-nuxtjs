<template lang="md">
  <div class="content">

# Lint/UriEscapeUnescape

* 概要
* 例
* なぜ？
* 回避する方法

## 概要

> This cop identifies places where `URI.escape` can be replaced by `CGI.escape`, `URI.encode_www_form` or `URI.encode_www_form_component` depending on your specific use case. Also this cop identifies places where `URI.unescape` can be replaced by `CGI.unescape`, `URI.decode_www_form` or `URI.decode_www_form_component` depending on your specific use case.

## 例

```ruby
# bad
URI.escape('http://example.com')
URI.encode('http://example.com')

# good
CGI.escape('http://example.com')
URI.encode_www_form([['example', 'param'], ['lang', 'en']])
URI.encode_www_form(page: 10, locale: 'en')
URI.encode_www_form_component('http://example.com')

# bad
URI.unescape(enc_uri)
URI.decode(enc_uri)

# good
CGI.unescape(enc_uri)
URI.decode_www_form(enc_uri)
URI.decode_www_form_component(enc_uri)
```

## なぜ？

[公式ガイド](https://docs.ruby-lang.org/ja/latest/method/URI/s/encode.html) にもあるように、URI.encode, URI.decode はobsoluteになっているため、将来の変更前に代替手段を取らなくてはなりません。

ただ、単純にURI.encode を CGI.escape や URI.encode_www_form に置き換えれば良いかと言うと、注意が必要です。

少し古い記事ですが、[こちら](http://d.hatena.ne.jp/riocampos+tech/20131025/p1) にも記載されているように、各々のメソッドで処理結果が違ってくる可能性があります。

## 回避する方法
### 記述行のみ

```ruby
URI.escape('http://example.com') # rubocop:disable Lint/UriEscapeUnescape
```

### 特定のメソッドのみ

```ruby
# rubocop:disable Lint/UriEscapeUnescape
def example
  URI.escape('http://example.com')
end
# rubocop:enable Lint/UriEscapeUnescape
```

### アプリケーション全体

```ruby
# .rubocop.yml
Lint/UriEscapeUnescape:
  Enabled: false
```
  </div>
</template>

<script>
export default {}
</script>
