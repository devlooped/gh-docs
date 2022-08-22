# GitHub Docs Theme

A Jekyll template that duplicates the GitHub Docs site design

## Building

Set the environment variable `JEKYLL_GITHUB_TOKEN` so that the 
`site.github` variable is properly populated, then run:

    bundle exec jekyll build --watch

Serve by changing to the `_site` dir and runing:

    dotnet serve

> For some reason, `bundle exec jekyll serve --incremental --watch` 
> results in an empty site/index page :/