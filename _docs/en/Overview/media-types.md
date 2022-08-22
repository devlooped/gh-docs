---
title: Media types
intro: Learn about media types for specifying the format of the data you want to consume.
---

Custom media types are used in the API to let consumers choose the format
of the data they wish to receive. This is done by adding one or more of
the following types to the `Accept` header when you make a request. Media types
are specific to resources, allowing them to change independently and support
formats that other resources don't.

All media types look like this:

    application/vnd.github.param[+json]

The most basic media types the API supports are:

    application/vnd.github+json
    application/json
