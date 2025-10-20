---
url: https://developer.wordpress.org/plugins/rest-api/rest-api-overview
scraped_at: 2025-10-20T03:18:22.629Z
---

[Skip to content](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

REST API Overview


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[REST API](https://developer.wordpress.org/plugins/rest-api/)REST API Overview

Search

# REST API Overview

## In this article

Table of Contents

- [Why use the WordPress REST API](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#why-use-the-wordpress-rest-api)
- [Key Concepts](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#key-concepts)
  - [Routes & Endpoints](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#routes-endpoints)
  - [Requests](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#requests)
  - [Responses](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#responses)
  - [Schema](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#schema)
  - [Controller Classes](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#controller-classes)
- [Next Steps](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#next-steps)

[↑ Back to top](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/#wp--skip-link--target)

The WordPress REST API brings many new features to WordPress. The REST API uses JSON (JavaScript Object Notation) as its data format.  JSON is an open standard data format that is becoming more widely used across the web as a whole, and software in general.  It is light-weight and human readable, and looks like Objects do in JavaScript; hence the name.  When you make a request to the API, the response will be returned in JSON. This enables developers to use WordPress in languages beyond PHP, which in turn allows WordPress to be used in new and exciting ways.

## [Why use the WordPress REST API](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#why-use-the-wordpress-rest-api)

There are many use cases for the WordPress REST API.  One of the largest use cases is creating Single Page Applications on top of WordPress.  You could create an entirely new admin experience for WordPress, or you could create an entirely new front end experience for WordPress.  You would not even have to write the applications in PHP.  Any programming language that can make HTTP requests and interpret JSON could be used to write something on WordPress.

The WordPress REST API can also serve as a strong replacement for the admin-ajax API in core.  By using the REST API, you can more easily structure the way you want to get data into and out of WordPress.  AJAX calls can be greatly simplified by using the REST API, enabling us to provide better user experiences in our work.

The use cases extend beyond these and really our imagination is the only limit to what can be done.  The bottom line is, if you want an structured, extensible, and simple way to get data in and out of WordPress, you probably want to use the REST API.  The API, for all of its simplicity, can be quite complex at first and we will attempt to break it down into smaller components so that we can easily piece together the larger puzzle.

## [Key Concepts](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#key-concepts)

To get started with using the WordPress REST API we will break down some of the key concepts and terms associated with the API:

- Routes/Endpoints
- Requests
- Responses
- Schema
- Controller Classes

Each of these concepts play a crucial role in using and understanding the WordPress REST API.  Let’s briefly break them down so that we can later explore each in greater depth.

### [Routes & Endpoints](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#routes-endpoints)

A route, in the context of the WordPress REST API, is a URI which can be mapped to different HTTP methods.  The mapping of an individual HTTP method to a route is known as an endpoint.  To clarify: If we make a `GET` request to `http://oursite.com/wp-json/`, we will get a JSON response showing us what routes are available, and within each route, what endpoints are available. `/wp-json/` Is a route itself and when a `GET` request is made it matches to the endpoint that displays what is known as the index for the WordPress REST API. We will learn how to register our own routes and endpoints in the following sections.

### [Requests](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#requests)

In the WordPress REST API infrastructure one of the primary classes is `WP_REST_Request`. The request class is used to store and retrieve information for the current request, requests can also be made internally within PHP to avoid using HTTP. `WP_REST_Request` objects are automatically generated for you whenever you make an HTTP request to a registered route. The data specified in the request will have an impact on what response you get back out of the API. There are a lot of neat things that can be done using the request class. The request section will go into greater detail.

### [Responses](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#responses)

Responses are the data you get back from the API. The `WP_REST_Response` provides a way to interact with the response data returned by endpoints. Responses can return the desired data, and they can also be used to return errors.

### [Schema](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#schema)

When we have responses and requests of different kinds of data, we need to be able to tell what type of data we are interacting with. Schema provides us a way to structure our data. Schema also provides security benefits for the API as it enables us to validate requests being made to the API. Schema is a large topic and we will get into that in the schema section.

### [Controller Classes](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#controller-classes)

As you can see the WordPress REST API has a lot of moving parts that all need to work together. Controller classes enable us to bring all of these elements together in a single place. With a controller class we will be able to manage the registering of routes & endpoints, handle requests, utilize schema, and generate responses.

## [Next Steps](https://developer.wordpress.org/plugins/rest-api/rest-api-overview/\#next-steps)

Let’s dive into how to register routes and endpoints for the REST API.

First published

August 26, 2021

Last updated

July 19, 2024

[PreviousREST APIPrevious: REST API](https://developer.wordpress.org/plugins/rest-api/)

[NextRoutes & EndpointsNext: Routes & Endpoints](https://developer.wordpress.org/plugins/rest-api/routes-endpoints/)

Notifications