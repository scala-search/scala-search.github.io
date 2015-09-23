---
layout: page
title: "Scaps: Scala API Search"
---

Scaps is a search engine for discovering functionality in Scala libraries (or in other words, a <a href="https://www.haskell.org/hoogle/">Hoogle</a> for Scala). You can use both type signatures and keywords in your search queries.

## Highlights

<div class="row">
  <div class="col-sm-6 col-md-4">
    <div class="thumbnail">
      <div class="caption">
        <h3>Type Search</h3>
        <p>Use a type signature in your query and Scaps will retrieve definitions with similar types.</p>
        <p>For example, <a href="http://scala-search.org/?q=Ordering%5BString%5D&m=org.scala-lang:scala-library:2.11.6&m=org.scalaz:scalaz-core_2.11:7.1.1"><code>Ordering[String]</code></a> also retrieves <code>Ordering.String</code> which is a subtype of the query type.</p>
      </div>
    </div>
  </div>
  <div class="col-sm-6 col-md-4">
    <div class="thumbnail">
      <div class="caption">
        <h3>Keywords & Operators</h3>
        <p>You can use keywords or operator names to search Scaps: <a href="http://scala-search.org/?q=%7C%40%7C&m=org.scala-lang%3Ascala-library%3A2.11.6&m=org.scalaz%3Ascalaz-core_2.11%3A7.1.1"><code>|@|</code></a></p>
        <p>Also mixing keywords and type signatures is possible: <a href="http://scala-search.org/?q=max%3A+Int&m=org.scala-lang%3Ascala-library%3A2.11.6&m=org.scalaz%3Ascalaz-core_2.11%3A7.1.1"><code>max: Int</code></a></p>
      </div>
    </div>
  </div>
  <div class="col-sm-6 col-md-4">
    <div class="thumbnail">
      <div class="caption">
        <h3>Scala Docs</h3>
        <p>When you have found a definition that seems interesting, you can directly navigate to the according Scala Doc entry by using the "Doc" link.</p>
      </div>
    </div>
  </div>
</div>

## News

<ul>
  {% for post in site.posts limit: 3 %}
  <li>{{ post.date | date: '%B %d, %Y' }} - <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## Authorship

Scaps is an offspring of a master's thesis by Lukas Wegmann at the <a href="http://www.hsr.ch/">University of Applied Science Rapperswil (HSR)</a>.
