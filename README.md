# stream-embed

A simple page for creating a Twitch Video embed for an arbitrary channel to embed in OBS as a Browser Source.


# Usage

This repository is published to GitHub pages to be served over HTTPS at https://faultyserver.github.io/stream-embed.

To specify the channel to embed, pass a hash parameter at the end of the URL. For example,

```
https://faultyserver.github.io/stream-embed/#amfaulty
```

Currently, the embed is configured to load the stream at 854x480 (480p equivalent) and a volume of 90%.

Below the embed are controls for passively interacting with the embed. Currently, only Volume is available as a control. This is a quick workaround for not being able to control the volume or routing of Browser Sources withing OBS.


# Rationale

A lot of video embedding APIs throw hundreds of errors in the console when the page they are embedded on is not using a secure protocol. For example, just loading a simple page with `file://` will cause the Twitch embed player to throw hundreds of errors.

The embeds will generally still work in this case, but having so many log errors is really quite annoying when all you want to do is get a video embed for use elsewhere.

In my case, I need to embed Twitch streams into an OBS scene to use in a marathon stream.

Having a public URL for this also means you don't need to copy and paste an HTML file around whenever you want to embed a stream.


This page also differs slightly from the standard Twitch popout player in that it explicitly hides user controls. Never worry about having them show up on your page again!
