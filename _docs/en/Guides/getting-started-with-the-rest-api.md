---
title: Getting started with the REST API
intro: 'Learn the foundations for using the REST API, starting with authentication and some endpoint examples.'
---

Let's walk through core API concepts as we tackle some everyday use cases.

## Overview

Most applications will use an existing [wrapper library][wrappers] in the language
of your choice, but it's important to familiarize yourself with the underlying API
HTTP methods first.

There's no easier way to kick the tires than through [cURL][curl]. If you are using
an alternative client, note that you are required to send a valid
[User Agent header](/rest/overview/resources-in-the-rest-api#user-agent-required) in your request.

### Hello World

Let's start by testing our setup. Open up a command prompt and enter the
following command:

```shell
$ curl https://api.github.com/zen

> Keep it logically awesome.
```

The response will be a random selection from our design philosophies.

## Authentication

Unauthenticated clients can make 60 requests per hour. To get more requests per hour, we'll need to
_authenticate_. In fact, doing anything interesting with the API requires
[authentication][authentication].

### Using personal access tokens

The easiest and best way to authenticate with the API is by using Basic Authentication [via OAuth tokens](/rest/overview/other-authentication-methods#via-oauth-and-personal-access-tokens). OAuth tokens include [personal access tokens][personal token].

Use a `-u` flag to set your username:

```shell
$ curl -i -u <em>your_username</em> /users/octocat

```


### Get your own user profile

When properly authenticated, you can take advantage of the permissions
associated with your account. For example, try getting:

```shell
$ curl -i -u <em>your_username</em>:<em>your_token</em> /user

> {
>   ...
>   "plan": {
>     "space": 2516582,
>    "collaborators": 10,
>    "private_repos": 20,
>    "name": "medium"
>  }
>   ...
> }
```

This time, in addition to the same set of public information we
retrieved earlier, you should also see the non-public information for your user profile. For example, you'll see a `plan` object in the response which gives details about the plan for the account.

### Using OAut

Apps that need to read or write private information using the API on behalf of another user should use OAuth.