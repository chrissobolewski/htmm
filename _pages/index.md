---
layout: page
title: Home
id: home
permalink: /
---

# Welcome! 💸

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
  All you need to pay off your [[Debt]], grow your [[Savings]], and make wise [[Investments]] decisions. Here you'll find reliable advice, real-life examples, and additional materials to help you manage your money better.
</p>

## Start here
- Read more <a class="internal-link" href="/about">about this page</a>.

### Fundamentals
- [[Spend less than you make]]
- [[Emergency fund]]

### Managing your personal budget
- [[Minimalist personal budget]]

## What's new?
Be always up to date — subscribe to my newsletter (no spam, just relevant notifications):

<div id="revue-embed">
  <form action="https://www.getrevue.co/profile/htmm/add_subscriber" method="post" id="revue-form" name="revue-form"  target="_blank">
  <div class="revue-form-group">
    <label for="member_email">Just enter</label>
    <input class="revue-form-field" placeholder="your email address" type="email" name="member[email]" id="member_email"> and <input type="submit" value="subscribe!" name="member[subscribe]" id="member_submit">
  </div>
  </form>
</div>

You can also follow the development of this site through <a href="https://twitter.com/howtomngmoney/">Twitter</a> and via my <a href="https://howtomanage.money/feed.xml">RSS feed</a>.
<ul>
 {% assign sorted = site.collection_name | sort: 'date' | reverse %}
    {% for item in sorted limit:3 %}
    <li>{{ item.title }}</li>
    {% endfor %}
</ul>
<style>
  .wrapper {
    max-width: 46em;
  }
</style>
