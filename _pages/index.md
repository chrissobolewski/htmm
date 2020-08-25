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

<script>
const fs      = require('fs');
const fetch   = require('node-fetch');
const parser  = require('xml2json');
const chalk   = require('chalk');


module.exports = {

  async onPreBuild({ inputs, utils }) {

    // Gather the data from all the specified feeds
    for (const feed of inputs.feeds) {

      // Where fetched data should reside in the buid
      let dataFilePath = `${inputs.dataDir}/${feed.name}.json`;

      // reinstate from cache if it is present
      if ( await utils.cache.has(dataFilePath) ) {
        await utils.cache.restore(dataFilePath);
        console.log('Restored from cache:', chalk.green(feed.url));
      }
      // Or if it's not cached, let's fetch it and cache it.
      else {
        var data = await fetch(feed.url)
          .then(async function(res) {

            // Stash all data as JSON.
            let contentType = res.headers.get('content-type').toLowerCase();
            if(contentType == 'application/json') {
              return res.json();
            } else {
              let text = await res.text();
              let json = parser.toJson(text);
              return JSON.parse(json);
            }
          });

        // put the fetched data in the daa file, and then cahce it.
        // await saveFeed(JSON.stringify(data), dataFilePath);
        await fs.writeFileSync(dataFilePath, JSON.stringify(data));
        await utils.cache.save(dataFilePath, { ttl: feed.ttl });
        console.log('Fetched and cached: ', chalk.yellow(feed.url), chalk.gray(`(TTL:${feed.ttl} seconds)`));

      }
    }
  }
}
</script>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
