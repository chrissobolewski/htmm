---
layout: page
title: Home
id: home
permalink: /
---

# Welcome! 💸

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
  This page is a resource for all things [[Savings]], [[Personal budget]], and [[Good financial habits]]. Reliable advice, real-life examples, and additional materials to help you manage your money better.
</p>

## Start here
- Read more <a class="internal-link" href="/about">about this page</a>.

### Learn the basics of personal finance
- [[Spend less than you make]]
- Build an [[Emergency fund]]
- Cultivate [[Good financial habits]]

### Manage your personal budget
- [[Minimalist personal budget]]

### Understand banking products and services better
- [[Credit card]]

## What's new?
Be always up to date — subscribe to my newsletter (no spam, just relevant notifications):

<div id="revue-embed">
  <form action="https://www.getrevue.co/profile/htmm/add_subscriber" method="post" id="revue-form" name="revue-form"  target="_blank">
  <div class="revue-form-group">
    <label for="member_email">Just enter</label>
    <input class="revue-form-field" placeholder="your email address" type="email" name="member[email]" id="member_email"> and <input type="submit" value="subscribe" name="member[subscribe]" id="member_submit">
  </div>
  </form>
</div>

You can also follow the development of this site through <a href="https://twitter.com/ksobny/">Twitter</a> and via my <a href="https://howtomanage.money/feed.xml">RSS feed</a>.

<h3>Latest entries</h3>

<ul>
 {% assign sorted = site.notes | sort: 'date' | reverse %}
    {% for item in sorted limit:5 %}
    <li><a class="internal-link" href="{{ item.url }}">{{ item.title }}</a></li>
    {% endfor %}
</ul>

## Find what you need
<form action="https://howtomanage.money/_pages/search.html" method="get">
  <label for="search-box">I want to know more about...</label>
  <input type="text" id="search-box" class="revue-form-field" name="query">
  <input type="submit" value="show me">
</form>

<hr>
<style>
  .wrapper {
    max-width: 46em;
  }
</style>
