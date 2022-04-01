# Layers

Think [Spaces] but without the isolation. Layer apps on top of each other and reliably swap to them with keyboard shortcuts.

OSX only. Depends on `ruby`, `xargs`, and `osascript` which should all be installed by default.

## Usage

- Clone this repo and cd into it
- Create `~/.layers` with a line for each layer of apps. Separate the apps by commas. Example below.
- `chmod +x layers`
- run `./layers`
- add keyboard shortcuts based on the output
  - I'm using Alfred Workflows for this, but any app that lets you run shell commands via keyboard shortcuts will work.

## Example ~/.layers file

Here's the `~/.layers` file I'm using at time of writing.

```
Alacritty
Firefox, Safari, Google Chrome
Slack
Messages, Music, Stream Deck
zoom.us
```

## How does it work?

Read the source and maybe [check out this blog post for more context][blog].

## How can I preserve app focus order in a layer?

By default, we use `-P 8` in the `xargs` keybinding to parallelize focussing apps. For layers where a deterministic app order is preferred, swap the `8` to a `1`.

## How can I preserve window focus order within a given app?

You can't yet. We focus each window for an app individually and the order is not currently deterministic.

[Spaces]: https://support.apple.com/guide/mac-help/work-in-multiple-spaces-mh14112/mac
[blog]: https://blog.semanticart.com/2022/04/01/layers/
