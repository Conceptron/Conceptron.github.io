# kritinsathi.com

Jekyll blog on GitHub Pages. Canonical home for everything; other platforms syndicate
back here.

## Local preview

```sh
bundle install
bundle exec jekyll serve --livereload
# http://127.0.0.1:4000
```

## Publishing a post

1. Drop the file in `_posts/` as `YYYY-MM-DD-slug.md`.
2. Front matter:

   ```yaml
   ---
   title: "Carries the words someone would actually type into Google"
   description: "Under 156 chars. Becomes the meta description and the SERP snippet."
   tags: [four, lowercase, tags, here]
   ---
   ```

3. Push to `main`. GitHub Pages builds it.
4. **Let Google index it before syndicating anywhere.** Check coverage in Search Console
   first — usually 1–3 days. Syndicating before the canonical is indexed is how the
   platform copy ends up outranking this one.

## Syndication order — this order is the whole point

Publish here → wait for indexing → then repost elsewhere with a canonical link back.

| Platform | How to set canonical |
|---|---|
| dev.to | `canonical_url:` in the post's front matter |
| Hashnode | "Original article URL" field in post settings |
| Medium | Import Story tool (sets `rel=canonical` automatically), **not** copy-paste |
| LinkedIn | No canonical field — post a *shortened adaptation* that links back, never the full text |
| Reddit | Link post or a plain-prose writeup; see below |

Without a canonical, Google sees several copies of the same page and will usually rank
the high-authority platform over this domain. That's the failure mode this whole setup
exists to avoid.

## Reddit rules of thumb

- Check the subreddit's self-promotion rules **before** posting. Several ban links outright.
- Don't cross-post identical text to multiple subreddits — it's against Reddit's
  Responsible Builder Policy and gets caught by spam filters anyway.
- Write it as plain paragraphs. No headers, no bullet frameworks, no bold section labels.
  Mod removals for "AI wall of content" are common and formatting is the tell.
- Post the substance in the thread body. "Full writeup on my blog" as the only content
  reads as a traffic grab and gets downvoted.

## Adding a custom domain

`CNAME` holds the domain. DNS at the registrar:

```
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
AAAA  @    2606:50c0:8000::153
AAAA  @    2606:50c0:8001::153
AAAA  @    2606:50c0:8002::153
AAAA  @    2606:50c0:8003::153
CNAME www  conceptron.github.io.
```

Then enable "Enforce HTTPS" in the repo's Pages settings once the cert provisions.

## Not in this repo

Drafts live in `../drafts/`. Nothing moves into `_posts/` until it has been through the
privacy audit and the fact-check pass.
