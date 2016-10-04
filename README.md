# Visiomatic on Docker

The container exposes port `80` and the directory `/data`, where images in `TIFF` format are meant to be found.

In this preliminary version only one image name `image.tif` is to be shown.

## How to use
Let us consider your `image.tif` is inside `/path/to/data` directory.

```
$ docker run --name visiomatic -v /path/to/data/image.tif:/app/image.tif -p 80:80 chbrandt/visiomatic
```

Now open in your browser `http://localhost`.
