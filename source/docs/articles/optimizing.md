---
title: Optimization for Pantheon and the Cloud
description: Learn how to optimize your site to efficiently function on Pantheon's cloud.  
category:
  - optimizing
  - drupal

---

Pantheon as a platform attempts to balance the tradeoff between high performance and high availability. It is important to reduce single points of failure and insure scalability, but this effort can introduce complexity and latency vs a “one box” architecture.  













1. **Varnish Caching:** Pantheon integrates a Varnish reverse-proxy caching layer, which is a standard tool for reducing the load on a Drupal site’s database and speeding anonymous responses. [Using Varnish](/docs/articles/architecture/edge/varnish) may mean reconfiguring how your site uses cookies, and making minor changes to cache configuration; no modules are required.
2. **Redis Caching:** By offsetting database requests [using redis](/docs/articles/sites/redis-as-a-caching-backend#understanding-redis-cache) as the caching backend, you can greatly reduce the number of round trips required to build a page. If you’ve written custom queries, use Drupal’s cache\_set and cache\_get to store and retrieve caches.
3. **Code/Query Optimization:** This may require analysis and refactoring of unwieldy queries or code optimization. In these circumstances, tools such as New Relic (included with every site), [Devel](https://drupal.org/project/devel), and the site’s slow query log (in the /logs directory) are valuable in determining the root of degraded or inefficient performance.
4. **Front End Optimization:** After a response has been built by Drupal, it needs to be transferred and rendered in the client browser. Reducing unnecessary markup, aggregating and compressing JavaScript and CSS, using a CDN for static content can help improve browser rendering time. Tools like [YSlow](http://yslow.org/) and Google's [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights)will identify bottlenecks.
5. **Module Evaluation:** Lowering the number of enabled modules will reduce the overhead required by Drupal to perform any operation.

In short, a lightweight site is a happy site. By taking steps to optimize your site to take advantage of a cloud architecture, you’ll improve your users site experience and satisfaction.

For additional tips for success on our platform, check out our [required reading](/docs/articles/required-reading-essential-pantheon-documentation) page.