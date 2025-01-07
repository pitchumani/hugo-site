---
date: '2025-01-07T19:12:41+05:30'
title: 'Create new post using Hugo'
tags:
  - hugo
  - new post
---
To create a new post in our site, run below command:
```
hugo new content content/posts/new-post.md
```
This will create 'new-post.md' file with [frontmatter](https://gohugo.io/content-management/front-matter/).
Remove the field 'draft' field from frontmatter once the post is ready to be
published.
By default hugo do not publish the draft posts. Don't worry, during development
we can include draft content using option `--buildDrafts` or `-D`.
To run hugo server:
```
hugo server
```
To run hugo server with draft content, use:
```
hugo server --buildDrafts
```

To deploy the hugo site to GitHub pages:
* Your site should be a repo in GitHub
* The repo has GitHub workflow to build and deploy hugo site GitHub pages
In this case, you can just push the new content md file to repo.
