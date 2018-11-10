### MetaTags
---
https://github.com/kpumuk/meta-tags

```
gem 'meta-tags'
rails g meta_tags:install

```

```
<head>
</head>

<h1></h1>

<head>
</head>
<body>
</body>

<>
<>
<>
<>
<>
<>

<>

<h1><%= title 'Member Login' %></hq>
<><><>

<>
<>
<>
<>
<>
<>

<meta property="og:title" content="my great view"></meta>

<>

<>
<>
<>

```

```ruby

@page_title = ''
@page_description = ''
@page_keywords = ''

set_meta_tags title: '',
              description: '',
              keywords: ''

class Decoument < ApplicationRecord
  def to_meta_tags
    {
      title: title,
      description: summary,
    }
  end
end
@document = Document.first
set_meta_tags @document

set_meta_tags title: [], site: ''
set_meta_tags title: [], reverse: true, site: ''

set_meta_tags keywords: []

display_meta_tags og: {
  title: :ttle,
  site_name: :site,
}

title 'my great view'

def default_meta_tags
  {
    title: '',
    description: '',
    keywords: '',
    separator: "".html_safe,
  }
end

set_meta_tags title: ''
set_meta_tags site: '', title: ''
set_meta_tags site: '', title: '', reverse: true

set_meta_tags description: "All text about keywords, other keywords"

set_meta_tags keywords: %w[]

set_meta_tags noindex: true
set_meta_tags noindex: 'googlebot'

set_meta_tags index: true

set_meta_tags nofollow: true
set_meta_tags nofollow: 'googlebot'

set_meta_tags noindex: true, follow: true
set_meta_tags canonical: ""

set_meta_tags icon: '/favicon.ico'
set_meta_tags icon: '', type: ''
set_meta_tags icon: [
  {},
  {}
]

set_meta_tags alternate: { "" => "" }
set_meta_tags alternate: { "" => "",
                           "" => "" }

set_meta_tags alternate: [
  { href: '', hreflang: '' },
  { href: '', type: '', title: '' },
  { href: '', media: '' }
]

set_meta_tags prev: ""
set_meta_tags next: ""

set_meta_tags image_src: ""
set_meta_tags amphtml: url_for()

set_meta_tags refresh: 5
set_meta_tags refresh: ''

set_meta_tags open_search: {}

set_meta_tags foo: {}

set_meta_tags of: {}

set_meta_tags og: {}

set_meta_tags og: {}

set_meta_tags article: {}

set_meta_tags twitter: {}

set_meta_tags twitter: {}

set_meta_tags sl: {}

set_meta_tags author: ""

set_meta_tags author: []
```
