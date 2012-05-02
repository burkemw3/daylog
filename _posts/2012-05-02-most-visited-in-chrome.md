---
title: Most Visited in Chrome
tags: OS X, Chrome
---

On OS X, Chrome stores browsing history in a sqlite file at ~/Library/Application Support/Google/Chrome/Default/History. I copied this file to my desktop and played around with a query to find my most visited sites. An example query is:

<pre>
SELECT
    urls.url,
    count(visits.id)
FROM urls
INNER JOIN visits ON visits.url = urls.id
WHERE
    urls.url NOT LIKE '%localhost%'
GROUP BY
    urls.id, urls.url
ORDER BY
    count(visits.id) DESC
LIMIT 100
</pre>

