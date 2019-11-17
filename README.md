# [Tefter](https://tefter.io)

![banner](https://i.imgur.com/xsKEdFk.jpg)

---

[Tefter](https://tefter.io) is a social bookmarking app for individuals and teams.

It's privacy focused, portable (mobile, desktop apps), has a growing list of integrations and
enables team collaboration.

![features-overview](https://i.imgur.com/lFJtSuR.png)


# Features

* [Intelligent Search](#intelligent-search)
  + [Autocomplete](#autocomplete)
* [Team Collaboration](#team-collaboration)
  + [Slack Integration](#slack-integration)
* [Aliases](#aliases)
* [Privacy](#privacy)
* [Feed](#feed)
* [Lists](#lists)
* [Data Import](#data-import)
* [Data Export](#data-export)
* [Recommendations](#recommendations)
* [Notes](#notes)
* [Favorites](#favorites)
* [Tags](#tags)
* [It's social](#its-social)
* [Smart Previews](#smart-previews)
* [Dead links discovery](#dead-links-discovery)
* [Readable mode](#readable-mode)
* [Apps](#apps)
    + [Desktop](#desktop)
    + [Mobile](#mobile)
    + [Browser Extensions](#browser-extensions)

## Intelligent Search

We index the contents of the pages you bookmark, but also calculate interesting metadata
like word count, reading time, author and topics for articles.

![search](https://i.imgur.com/2Mlxg23.png)

### Autocomplete

You can search as you type and see results of lists, bookmarks, tags and domains.

![autocomplete](https://i.imgur.com/sGODGRP.gif)

## Team Collaboration

You can create organizations, invite people and collectively add and organise your bookmarks.

![orgs-list](https://i.imgur.com/cHB15XF.png)

### Slack Integration

### Aliases

You can create shortcuts to links you commonly use. We call such shortcuts `aliases`.
Aliases can either be private for a user or they can be global for an
organization.

![list-aliases](https://i.imgur.com/aZvW1QV.png)

You can use the {web, mobile, desktop} UI to create a new alias, or you
can use the Slack integration.

For example, let's say you assign an alias to `https://security-tracker.debian.org/tracker/source-package/{{*}}`
to `deb-sec`.

![new-alias](https://i.imgur.com/LlN0JNB.png)

Then when you navigate to `https://tefter.io/go/deb-sec/nginx` you'll be redirected to
`https://security-tracker.debian.org/tracker/source-package/nginx`.

Aliases can be static, or dynamic. Dynamic aliases contain variable segments. Use `{{*}}` to create dynamic segments.

So, an alias `ex` pointing to `https://example.com/{{*}}/a/{{*}}/b/{{*}}` when invoked with
`go/ex/1/2/3` will redirect to `https://example.com/1/a/2/b/3`.

**Browser Extension**

You can use the browser extension to quickly navigate using aliases.
This is currently only available in Chrome.

![aliases-extension](https://i.imgur.com/oxoYBtu.gif)

**Command-Line Usage**

We're working on command-line application you can use to interact with Tefter.
Until it's released you can use a simple shell function like the following to navigate using aliases.

```shell
# Add this to your .zshrc
te() {
  open "https://tefter.io/go/$1"
}
```

![terminal-app](https://i.imgur.com/EJw1Hx6.gif)

**Coming Soon**

Functions in dynamic aliases.

## Privacy

We don't sell your data. Anything you post won't be public to other
users unless you explicitly decide to share it. Your whole profile can
be unlisted via Privacy Settings -> "Allow others to discover my
profile" (uncheck).

## It's social

## Feed

There's variety of news sources you can subscribe to and create a personalized feed of the latest and most interesting
things to read. When you follow users and they share bookmarks, they will also appear in your feed.

![feeds-list](https://i.imgur.com/aWPvmJO.png)

**Filtering**

You can search and apply filters in any of our feeds.

![feeds-search](https://i.imgur.com/DqlDDK4.png)

For example, you can search across [awesome](https://awesome.re) lists
for Elixir libraries around [Ecto](https://github.com/elixir-ecto/ecto), using https://tefter.io/~awesome/bookmarks?q=elixir&tags=ecto

## Lists

Lists are a way to organize your bookmarks.

![lists](https://i.imgur.com/tQ3hgCo.png)

### List Subscriptions

You can subscribe to lists and be notified each time a bookmark is added.

![list-subscriptions](https://i.imgur.com/aR5y6O5.png)

## Data Import

You can import bookmarks from Pocket, Pinboard or the browser.

### Data Export

You can effortlessly export all your data in JSON format. You don't have
to worry about lock-in or Tefter becoming unavailable.

## Recommendations

We display recommendations based on your bookmarks, so that you can keep discovering interesting content.

![recommendations](https://i.imgur.com/mcMi5X0.png)

## Notes

You can write notes using Markdown on your bookmarks and lists.

### Favorites

We keep a "special" 🌈 list of bookmarks you've marked as favorites.

![mark-as-favourite](https://i.imgur.com/wA4ihZC.png)


## Tags

You can add any number of tags to your bookmarks.
Tags provide a supplementary to lists way to organize bookmarks.
We do our best to suggest relevant tags. You can filter your bookmarks
by any combination of tags.

![tags](https://i.imgur.com/c4qHGU2.png)

## Smart Previews

For some websites, you can access the bookmarked content without leaving Tefter.

![smart-previews-youtube](https://i.imgur.com/ZJ874lI.png)

We also do our best to annotate such bookmarks with relevant tags and title.

For YouTube, we're fine-tuning a feature, where for songs, we'll be
indexing lyrics. 

So, given you've bookmarked https://www.youtube.com/watch?v=UelDrZ1aFeY
Searching for:

> I don't want to leave her now

Will surface "The Beatles - Something" bookmark. Cool right?


## Dead links discovery

We regularly check when your bookmarked pages are still available and
you can filter and delete dead ones.

**Filter by dead links**

![filter-dead-links](https://i.imgur.com/SdFHzs4.png)

**Access the archived page**

![read-the-archive](https://i.imgur.com/bs2X7cr.png)

### Readable Mode

For some of the pages you bookmark, we process them so that you can have
a clutter free experience, without ads, trackers or any kind of noise.

Example:

![readable](https://i.imgur.com/Pmx82aq.png)

## Public API

We have a [public API](https://tefter.io/docs/api) you can use to build apps or automate any part of
your bookmarking experience.


## Archiving

We store the contents of bookmarked pages, so that you can access them
even in the occasion they're down.

## Apps

### Desktop

![desktop-app](https://i.imgur.com/TggU5w2.png)

To download, see [here](https://github.com/tefter/desktop#downloads)

### Mobile

When you have the mobile app installed, you can quickly add bookmarks by sharing links to Tefter.

![share-to-tefter](https://i.imgur.com/yHrmMqE.jpg?1)

### Browser Extensions

You can quickly add bookmarks clicking on the Tefter extension icon.

![chrome-extension](https://i.imgur.com/rRhI3xe.png)

* [Chrome / Brave](https://chrome.google.com/webstore/detail/tefter/eldofalegbgagpenjjcapjaogpioldoh)
* [Firefox](https://addons.mozilla.org/en-US/firefox/addon/tefter/)
* [Bookmarklet](https://tefter.io/faq#bookmarklet)

# Feedback

There are multiple ways to provide feedback:

* Via [email](mailto:support@tefter.io)
* Our [Spectrum community](https://spectrum.chat/tefter)
* Our [feedback form](https://www.tefter.io/feedback/new)
* Follow us on [Twitter](https://twitter.com/Tefter_io)
