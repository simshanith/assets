# assets

Screenshots and other media linked from pull requests and issues.

## Layout

One branch per pull request, named for where the images are used:

```text
<owner>/<repo>/pr/<number>
```

Each branch is an orphan: it holds only that pull request's images, at the
root of the tree. Link an image by commit SHA so the link survives a reshoot:

```text
https://raw.githubusercontent.com/simshanith/assets/<sha>/<file>.png
```

To reshoot, add a commit on the same branch and update the links.

## Retention

[`cleanup.yml`](.github/workflows/cleanup.yml) runs weekly and deletes a
branch once its pull request has been closed or merged for 90 days. Links to a
deleted branch's commits stop working some time after that. A branch whose
name does not end in `pr/<number>` is never deleted.
