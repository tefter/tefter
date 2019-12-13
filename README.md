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
      + [Login](#login-5)
      + [Searching](#searching-1)
      + [Sharing](#sharing-search-results-with-others)
      + [Creating an alias](#creating-an-alias)
      + [Resolving an alias](#resolving-an-alias)
      + [Listing all aliases](#listing-all-aliases)
      + [Listing the most popular bookmarks](#listing-the-most-popular-bookmarks)
* [Aliases](#aliases)
* [Privacy](#privacy)
* [It's social](#its-social)
* [Feed](#feed)
* [Lists](#lists)
  + [Sharing](#private-list-sharing)
* [Tags](#tags)
* [Favorites](#favorites)
* [Notes](#notes)
* [Data Import](#data-import)
* [Data Export](#data-export)
* [Recommendations](#recommendations)
* [Explore](#explore)
* [Smart Previews](#smart-previews)
* [Dead links discovery](#dead-links-discovery)
* [Archiving](#archiving)
* [Public API](#public-api)
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

Creating a Tefter organization is free for up to 5 seats. A seat is
reserved for members who can add / edit / delete content. Read-only
operations don't require occupying a seat, meaning that even in the free
tier all the members of the org can search and use aliases.

We're committed to give back to open-source, so such communities can use
Tefter for free without any limitations. Just shoot an [email](support@tefter.io) and we'll
be happy to upgrade your plan.

### Slack Integration

You can interact with Tefter on Slack using either commands or mentions.

To invoke commands use either `/tefter <command>` or the shorter equivalent `/t <command>`.
For mentions use `@tefter <command>`.

#### Login

Any Slack workspace member who wishes to create or modify content of
Tefter for the organization has to log in first. By logging in a Slack
member account is connected to a Tefter one.

Use `/t login` to connect your accounts.

**Adding bookmarks**

You can use the `/t <url>` command or a Slack
message action to add a bookmark.

<details>
  <summary>
  Demo of the command
  </summary>

  <img src="https://i.imgur.com/YBYWJyd.gif" alt="slack integration add bookmark">
</details>

<details>
  <summary>
  Demo of the message action
  </summary>

  <img src="https://i.imgur.com/VQQ2OxX.gif" alt="slack integration add bookmark">
</details>

<br/>

#### Searching

You can use the `/t search <query>` command or mention the
`@tefter` bot to search.

An example using the mention might be:

`Yo @tefter search functional programming`

💡 There's a short version of the search command. It's just `s`.  
Example: `/t s agile`

<details>
  <summary>
  Demo of the search command
  </summary>

  <img src="https://i.imgur.com/4wqaTL4.gif" alt="slack integration search command">
</details>

<br/>

#### Sharing search results with others

When searching for any results that you wish to share to the members of
the channel, you can select "share".

<details>
  <summary>
  Demo of the sharing action
  </summary>

  <img src="https://i.imgur.com/raQBXG9.png" alt="slack integration share action">

  <img src="https://i.imgur.com/rVmMTVj.png" alt="slack integration share action response">
</details>

<br/>

Keep in mind that @tefter has to be invited to that channel first.

#### Creating an alias

`/t alias <alias> <url_pattern>`


Example:

`/t alias api-docs https://tefter.io/docs/api`

or with a dynamic alias

`/t alias deb-tracker https://tracker.debian.org/pkg/{{*}}`

Read more about aliases in the section below.

#### Resolving an alias

`/t <alias_pattern>`

Example:

`/t deb-tracker/nginx`

or by mentioning `@tefter`

`@tefter deb-tracker/nginx`

#### Listing all aliases

`/t aliases`

or by mentioning `@tefter`

`@tefter aliases`

#### Listing the most popular bookmarks

`/t news`

Our ranking algorithm factors in recency, likes and views.

![tefter-news-command](https://i.imgur.com/XmrFUhs.png)

### Aliases

You can create shortcuts to links you commonly use. We call such shortcuts `aliases`.
Registering an `api-docs` to `https://verylongnameapplication.com/api-docs` allows you to
type `go/api-docs` in your browser's address bar to navigate there.
Think of it as a https://www.golinks.io/ alternative.

Aliases can either be private for a user or they can be global for an organization.

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

**Search bar**

You may also navigate using aliases from the search bar.

![search-bar-demo](https://i.imgur.com/oGRZVSI.gif)

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

### Bookmarks Import

We're working on functionality to import bookmarks to your organizations.
Meanwhile if you need any support importing bookmarks from any source to
your org, let us know, we'll be happy to help.

## Privacy

We don't sell your data. Anything you post won't be public to other
users unless you explicitly decide to share it. Your whole profile can
be unlisted via Privacy Settings -> "Allow others to discover my
profile" (uncheck).

## It's social

You can follow users and see in your feed bookmarks they decided to share.
You may also like any of the bookmarks appearing in your feed.

![feed-like](https://i.imgur.com/00OOgA6.png)

**Karma Points**

Share interesting stuff and you may collect karma points.

![karma-points](https://i.imgur.com/KnLjjso.png)

## Feed

There's variety of news sources you can subscribe to and create a personalized feed of the latest and most interesting
things to read. When you follow users and they share bookmarks, they will also appear in your feed.

![feeds-list](https://i.imgur.com/aWPvmJO.png)

**Filtering**

You can search and apply filters in any of our feeds.

![feeds-search](https://i.imgur.com/DqlDDK4.png?1)

For example, you can search across [awesome](https://awesome.re) lists
for Elixir libraries around [Ecto](https://github.com/elixir-ecto/ecto), using https://tefter.io/~awesome/bookmarks?q=elixir&tags=ecto

**Domains**

Clicking on the domain of a bookmark, filters bookmarks by that domain.

## Lists

Lists are a way to organize your bookmarks.

![lists](https://i.imgur.com/tQ3hgCo.png)

They can either be public, which means that anyone can view them or private.

### Private List Sharing

You can share private lists to anyone on the internet, by generating a
special "share" link.

![private-list-sharing](https://i.imgur.com/fvsyFaz.png)

### List Subscriptions

You can subscribe to lists and be notified each time a bookmark is added.

![list-subscriptions](https://i.imgur.com/aR5y6O5.png)

## Tags

You can add any number of tags to your bookmarks.
Tags provide a supplementary to lists way to organize bookmarks.
We do our best to suggest relevant tags. You can filter your bookmarks
by any combination of tags.

![tags](https://i.imgur.com/c4qHGU2.png)

## Data Import

You can import bookmarks from Pocket, Pinboard, Google bookmarks or most popular browsers.

![bookmarks-import](https://i.imgur.com/FT94kcq.png)

### Data Export

You can effortlessly export all your data in JSON format. You don't have
to worry about lock-in or Tefter becoming unavailable.

## Recommendations

We display recommendations based on your bookmarks, so that you can keep discovering interesting content.

![recommendations](https://i.imgur.com/mcMi5X0.png)

## Explore

There's https://tefter.io/explore where you can wander and find
interesting things to read from our feeds or find users to follow.

![explore](https://i.imgur.com/TyYPIMW.png)

## Notes

You can write notes using Markdown on your bookmarks and lists.

### Favorites

We keep a "special" 🌈 list of bookmarks you've marked as favorites.

![mark-as-favourite](https://i.imgur.com/wA4ihZC.png)

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

**Installation**

You can install Tefter as a progressive web app. See [how](https://twitter.com/Tefter_io/status/1106145149019742210).

**Android App**

The app will be available on Google Play soon.

### Browser Extensions

**Add bookmark**

You can quickly add bookmarks clicking on the Tefter extension icon.

![chrome-extension](https://i.imgur.com/rRhI3xe.png)

**Search**

Or you can search straight from the address bar, by typing `t` followed by the `tab` key.

![chrome-omnibar](https://i.imgur.com/O29gxoR.gif)

**Install**

* [Chrome / Brave](https://chrome.google.com/webstore/detail/tefter/eldofalegbgagpenjjcapjaogpioldoh)
* [Firefox](https://addons.mozilla.org/en-US/firefox/addon/tefter/)
* [Bookmarklet](https://tefter.io/faq#bookmarklet)

# Feedback

There are multiple ways to provide feedback:

* Via [email](mailto:support@tefter.io)
* Our [Spectrum community](https://spectrum.chat/tefter)
* Our [feedback form](https://www.tefter.io/feedback/new)
* Follow us on [Twitter](https://twitter.com/Tefter_io)
