---
url: https://developer.wordpress.org/apis/making-http-requests/performance
scraped_at: 2025-10-20T04:10:55.116Z
attempt: 1
---

[Skip to content](https://developer.wordpress.org/apis/making-http-requests/performance/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Performance


[Home](https://developer.wordpress.org/)[Common APIs Handbook](https://developer.wordpress.org/apis/)[Making HTTP requests](https://developer.wordpress.org/apis/making-http-requests/)Performance

Search

# Performance

## In this article

Table of Contents

- [Caching](https://developer.wordpress.org/apis/making-http-requests/performance/#caching)
- [Check Headers](https://developer.wordpress.org/apis/making-http-requests/performance/#check-headers)

[↑ Back to top](https://developer.wordpress.org/apis/making-http-requests/performance/#wp--skip-link--target)

When you make an HTTP request, your application has to wait for the external server to respond to the request and for all the data to be transferred over the network. This can be very time consuming, and your application performance might be heavily impacted.

## [Caching](https://developer.wordpress.org/apis/making-http-requests/performance/\#caching)

That’s why you should always consider caching your API requests, so you don’t have to do them all the time.

Caching the response means storing the response on your server so you can easily use it multiple times without the need of an HTTP request every time.

For example, let’s say your site makes an HTTP request to Github to fetch your user’s stats and display it on your sidebar. If you don’t cache, every visitor in your site will trigger that API request and wait for github to response. And if you stop and think, they are all seeing the same information, because your stats don’t change so fast.

In the other hand, if you use cache, only the first visitor will have to wait for Github to respond. All the next users will see the same information that was quickly grabbed from the local database.

You can then define how often this information has to be updated. In other words, how often the cache has to be cleaned.

There are multiple apporaches to caching. An easy one provided by WordPress is the [Transient API](https://developer.wordpress.org/apis/handbook/transients/). Check it out!

## [Check Headers](https://developer.wordpress.org/apis/making-http-requests/performance/\#check-headers)

Many APIs allow you to make a HEAD request to check the status of things before actually retrieving the data you want. For example, you can make a HEAD request to check if there’s an update, before doing a GET request to actually fetch the data. This is a much faster request because it only responds a short piece of information.

Check the Advanced > Headers section for more information.

First published

July 13, 2020

Last updated

July 13, 2020

[PreviousPOSTing data to an external servicePrevious: POSTing data to an external service](https://developer.wordpress.org/apis/making-http-requests/posting-data-to-an-external-service/)

[NextAdvancedNext: Advanced](https://developer.wordpress.org/apis/making-http-requests/advanced/)

Notifications