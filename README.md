# A guestbook formatter based on HTML for [telegram-history-dump][1]

This formatter is a modified copy of the `html` formatter from [telegram-history-dump][1]. It is designed to create a digital guestbook from a telegram chat group.


## Some differences to `html`

- The output directory of the formatter shall contain all files necessary to open and render the html pages. So all media files are copied to the output firectory. References in HTML pages direct to the copied files.
- In the guestbook there is no difference between yourself and other authors. Your speech balloon looks like the others and contains your name.
- Each HTML page of a dialog have got a background image and a headline image which may be the avatar photo of your chat group. For this you have to copy some JPEGs to `formatters/guestbook-data/resources` which contains a `README.md` that you should read.
- The `index.html` has got a background image to. This is taken from `formatters/guestbook-data/resources/background.jpg`.
- The speech balloon of a geo message contains an iframe to display the map section.


## Installation

Copy and merge the directory `formatters` to your installation of [telegram-history-dump][1].


## Configuration

Add the new `guestbook` formatter. The option keys are the same as in `html`.

```
formatters:
#  ...
  guestbook:
    paginate: 0 # messages per page
    use_utc_time: false
    timestamps_every: 50 # messages
```

It's recommended to download and copy all media files:

```
download_media:
  photo: true
  document: true
  audio: true
  video: true
copy_media: true
```



[1]: https://github.com/tvdstaaij/telegram-history-dump
