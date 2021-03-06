# RedditFlow

An example [Flow](https://github.com/elixir-lang/flow) application that
aggregates word counts for specified subreddits (for now).

## Overview

- Stream comments/posts from reddit
- For each subreddit, track word count
  - Where do we track this?
- Supervise each subreddit

## Fake Subreddit

Here's a stream of fake data

```elixir
RedditFlow.FakeSubreddit.stream
|> Stream.map(&IO.inspect/1)
|> Stream.take(3)
|> Stream.run
```

## Usage

To see a sorted list of most frequently used words in a subreddit:

```elixir
TableAggregator.run["all"] |> Enum.sort_by fn({_, value}) -> -value end
```
