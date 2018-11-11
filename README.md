### MetaTags
---
https://github.com/kpumuk/meta-tags

```
gem 'meta-tags'
rails g meta_tags:install
```

```html
<head>
  <%= display_meta_tags site: 'My website' %>
</head>

<h1><%= title 'My page title' %></h1>

<head>
  <title>My website | My page title</title>
</head>
<body>
  <h1>My page title</h1>
</body>

<% title 'Member Login' %>
<% description 'Member login page.' %>
<% keywords 'Site, Login, Members' %>
<% nofollow %>
<% noindex %>
<% refresh 3 %>

<% set_meta_tags title: 'Member Login',
                 description: 'Member loginpage.',
                 keywords: 'Site, Login, Members' %>

<h1><%= title 'Member Login' %></hq>
<h1><%= title 'Member Login' %></h1>

<h1><%= title 'Member Login', 'Here you can login to the site:' %></h1>
<%= display_meta_tags separator: "".html_safe %>
<%= display_meta_tags lowercase: true %>
<%= display_meta_tags reverse: true, prefix: false %>
<%= display_meta_tags og: { title: 'The Rock', type: 'video.movie' } %>
<%= display_meta_tags alternate: { 'zh-Hant' => 'http://example.com.tw/base/url' } %>

<meta property="og:title" content="my great view"></meta>

<%= display_meta_tags(default_meta_tags) %>

<% title "My Page title" %>
<%= content_tag :div, data: { title: display_title(default_meta_tags) } do %>
  <h1><%= title %></h1>
<% end %>
```

```ruby

@page_title = 'Member Login'
@page_description = 'Member login page.'
@page_keywords = 'Site, Login, Members'

set_meta_tags title: 'Member Login',
              description: 'Member login page.',
              keywords: 'Site, Login, Members'

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
    title: 'Member Login',
    description: 'Member login page.',
    keywords: 'Site, Login, Members',
    separator: "&mdash;".html_safe,
  }
end

set_meta_tags title: 'Member Login'
set_meta_tags site: 'Site Title', title: 'Member Login'
set_meta_tags site: 'Site Title', title: 'Member Login', reverse: true

set_meta_tags description: "All text about keywords, other keywords"

set_meta_tags keywords: %w[keyword1 Keyowrd2 Keyword3]

set_meta_tags noindex: true
set_meta_tags noindex: 'googlebot'

set_meta_tags index: true

set_meta_tags nofollow: true
set_meta_tags nofollow: 'googlebot'

set_meta_tags noindex: true, follow: true
set_meta_tags canonical: "http://yoursite.com/canonical/url"

set_meta_tags icon: '/favicon.ico'
set_meta_tags icon: '/favicon.png', type: 'image/png'
set_meta_tags icon: [
  { href: '/images/icon_96.png', sizes: '32x32 96x96', type: 'image/png' },
  { href: '/images/icons/icon_itouch_precomp_32.png', rel: 'apple-touch-icon-precomposed', sizes: '32x32', type: 'image/png' }
]

set_meta_tags alternate: { "fr" => "http://yoursite.fr/alternate/url" }
set_meta_tags alternate: { "fr" => "http://yoursite.fr/alternate/url",
                           "de" => "http://yoursite.de/alternate/url" }

set_meta_tags alternate: [
  { href: 'http://example.fr/base/url', hreflang: 'fr' },
  { href: 'http://example.com/feed.rss', type: 'application/rss+xml', title: 'application/rss+xml', title: 'RSS' },
  { href: 'http://m.example.com/page-1', media: 'only screen and {max-width: 640px}' }
]

set_meta_tags prev: "http://yoursite.com/url?page=1"
set_meta_tags next: "http://yoursite.com/url?page=3"

set_meta_tags image_src: "http://yoursite.com/icons/icon_32.png"
set_meta_tags amphtml: url_for(format: :amp, only_path: false)

set_meta_tags refresh: 5
set_meta_tags refresh: '5;url=http://example.com'

set_meta_tags open_search: {
  title: "Open Search",
  href: "/opensearch.xml"
}

set_meta_tags foo: {
  bar: "lorem",
  baz: {
    qux: "ipsum"
  }
}

set_meta_tags og: {
  image: ["http://example.com/rock.jpg", "http://example.com/rock2.jpg"]
}

set_meta_tags og: {
  title: 'The Rock',
  type: 'video.movie',
  url: 'http://www.imdb.com/title/tt0117500/',
  image: 'http://ia.media-imdb.com/rock.jpg',
  video: {
    director: 'http://www.imdb.com/name/nm0000881/',
    writer: ['http://www.imdb.com/name/nm0918711/', 'http://www.imdb.com/name/nm0177018/']
  }
}

set_meta_tags og: {
  title: 'Two structured image properties',
  type: 'website',
  url: 'view-source:http://examples.opengraphrotocol.us/image-array.html',
  image: [{
    _: 'http://examples.opengraphprotocol.us/media/images/75.png',
    width: 75,
    height: 75,
  },
  {
    _: 'http://examples.opengraphprotocol.us/media/images/50.png',
    width: 50,
    height: 50,
  }]
}

set_meta_tags article: {
  published_time: '2018-11-11T03:34:00+01:00',
  modified_time: '2018-11-11T18:08:47+01:00',
  section: 'Article Section',
  tag: 'Article Tag'
}

set_meta_tags twitter: {
  card: "summary",
  site: "@username"
}

set_meta_tags twitter: {
  card: "photo",
  image: {
    _: "http://example.com/1.png",
    widht: 100,
    height: 100,
  }
}

set_meta_tags al: {
  ios: {
    url: "example://applinks",
    app_store_id: 12345,
    app_name: "Example App"
  }
}

set_meta_tags author: "Dmytro Shteflyuk"

set_meta_tags author: [ "Dmytro Shteflyuk", "John Doe" ]
```
