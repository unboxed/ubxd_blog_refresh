---
layout: "blog"
date: "2010-07-30 13:00:00 UTC"
published: true
title: "Announcing: Tabnav"
author: "Alex Tomlins"

---

I've just released a new gem called [Tabnav](http://rubygems.org/gems/tabnav). It's a Rails helper for generating navbars. It allows you to specify highlighting rules for each nav item in a clean way without lots of conditionals in your views.

It is loosely based on the widget from [rails-widgets](http://github.com/paolodona/rails-widgets), and uses a similar DSL. You may ask why I bothered writing this if something similar already exists. Well, simply, there are some things about the rails-widgets implementation that I really don't like. Specifically, it hijacks <tt>javascript_include_tag</tt> to insert it's own javascript. This sort of thing should be explicit. Also the markup it generates could be cleaner - it has some unnecessary extra tags in it, and repeated class names. I created this to clean up these problems, and add new features. I've added support for custom partials for tab contents, and I plan to add support for nested menus in the next version.

So how does it work? Well, that's easiest to show with some examples...

### A Basic Navbar

In the view:

<script src="http://gist.github.com/498861.js?file=gistfile1.erb"></script><noscript>
<pre><code>&lt;%
  render_tabnav do |n|
    n.add_tab do |t|
      t.named "Home"
      t.links_to root_path
      t.highlights_on :controller =&gt; :home, :action =&gt; :index
    end
    n.add_tab do |t|
      t.named "Froobles"
      t.links_to froobles_path
      t.highlights_on :controller =&gt; :froobles
    end
  end
%&gt;</code></pre>
</noscript>

When rendering the home page

<script src="http://gist.github.com/498861.js?file=gistfile2.html"></script><noscript>
<pre><code>&lt;ul&gt;
  &lt;li class="active"&gt;&lt;a href="/"&gt;Home&lt;/a&gt;&lt;/li&gt;
  &lt;li&gt;&lt;a href="/froobles"&gt;Froobles&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
</code></pre>
</noscript>

It allows lots of control over the generated markup:

In the view:

<script src="http://gist.github.com/498861.js?file=gistfile3.erb"></script><noscript>
<pre><code>&lt;%
  render_tabnav :id =&gt; "main_navigation", :class =&gt; "clearfix" do |n|
    n.add_tab :class =&gt; "home_tab" do |t|
      t.named "Home"
      t.links_to root_path
      t.highlights_on :controller =&gt; :home, :action =&gt; :index
    end
    n.add_tab :class =&gt; "heading" do |t|
      t.named "Froobles Heading"
      t.highlights_on :controller =&gt; :froobles
    end
    n.add_tab do |t|
      t.named "Froobles"
      t.links_to froobles_path, :target =&gt; "_blank", :rel =&gt; "http://foo.bar/"
      t.highlights_on :controller =&gt; :froobles, :action =&gt; :index
    end
  end
%&gt;
</code></pre>
</noscript>

On froobles/index outputs:

<script src="http://gist.github.com/498861.js?file=gistfile4.html"></script><noscript>
<pre><code>&lt;ul id="main_navigation" class="clearfix"&gt;
  &lt;li class="home_tab"&gt;&lt;a href="/"&gt;Home&lt;/a&gt;&lt;/li&gt;
  &lt;li class="heading active"&gt;&lt;span&gt;Froobles Heading&lt;/span&gt;&lt;/li&gt;
  &lt;li class="active"&gt;&lt;a href="/froobles" target="_blank" rel="http://foo.bar/"&gt;Froobles&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
</code></pre>
</noscript>

and if that's not enough for you, you can even specify your own partial to be used to render the tab contents.

Check out the [github project page](http://github.com/unboxed/tabnav) for full documentation etc. For feature requests or bug reports use the [github issue tracker](http://github.com/unboxed/tabnav/issues).

Enjoy.


