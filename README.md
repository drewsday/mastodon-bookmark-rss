# mastodon-bookmark-rss

A small web service to let you connect your mastodon bookmarks to your RSS reader.

Save interesting posts found on Mastodon into your read-it-later list by using Mastodon's bookmark function.

Use the instance at [woodland.cafe](https://bookmark-rss.services.woodland.cafe) or explore the options for self-hosting below.

## Linking behavior

Normally the generated RSS feed links to the respective bookmarked Mastodon
post. However, if the Mastodon post itself contains a link to another website,
the RSS item will use the link and title from that website, or rather from
Mastodon's link preview.

The purpose of this is to allow automatic prefetching and saving of article
content, which is a feature found in a few RSS readers such as Inoreader. In
those cases Mastodon (and Twitter) is just being used as a glorified link
aggregator.

The original Mastodon post URL and content is still stored in the RSS
`<content:encoded>` tag, so that additional context can be recovered.

## Operating it yourself

Please see [docs/deploy.md](docs/deploy.md).

## Running it locally

1. Clone this repository
2. Have Rust, Node and Yarn installed. I recommend [rustup](https://rustup.rs/)
   for Rust and [Volta](https://volta.sh/) for installing both Node and Yarn.
3. Install [entr](http://eradman.com/entrproject/)
4. Run `yarn install && yarn dev` to get a devserver at `localhost:3000`

To get a standalone release binary, run `yarn install && yarn build && cargo build --release`.

## License

MIT, see `LICENSE`.
