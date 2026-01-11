# fah-beta-mgr

`fah-beta-mgr` is a `bash` script which manages FAH beta binaries, so
you don't have to. It assumes that it's running in a
`systemd`-flavored Linux distro. Here's what it does:

- Maintains an A/B setup of `fah-client` binaries, which can be
  switched between at any time
  - So if a new beta is problematic, a single command will restart FAH
    with the previous version
- Checks for new beta releases of `fah-client`
- If one exists, it is downloaded and becomes the new 'A' `fah-client`
  binary
  - And previous 'A' binary becomes the new 'B' binary
  - Unless the 'B' binary was active, in which case it is retained
- The script can self-update, upon request

Absolutely not guaranteed to be bug-free, but my publishing toolchain
requires a clean pass of `shellcheck` before updating this site. Made
available under the [MIT license](https://opensource.org/license/MIT)


## Getting started

- Download the script [here](https://github.com/firepear/fah-beta-mgr/raw/refs/heads/main/fah-beta-mgr)
- Or [give it a read
  first](https://github.com/firepear/fah-beta-mgr/blob/main/fah-beta-mgr),
  if you like
- As root, run `/path/to/fah-beta-mgr setup`
  - This will move the script to `/usr/local/bin` and do other
    setup tasks
- Run `fah-beta-mgr update` to fetch the current beta FAH client and
  make it the active binary
  - Repeat this whenever you want to check for a new beta
- See `fah-beta-mgr help` and/or the rest of this document, for more options

## (Some) More options

### Update your FAH client

```
$ sudo ./fah-beta-mgr upgrade
checking for update... v8.5.5 available; updating... done
```

### Check FBM status

```
$ fah-beta-mgr status
fah-client is pointed to FAH-A
FAH-A: v8.5.5
FAH-B: v8.5.4
```

### Update FBM

```
$ fah-beta-mgr version
v0.6.0
$ sudo ./fah-beta-mgr fbm-up
checking for fbm update... new version of fbm found and installed
$ fah-beta-mgr version
v0.7.0
```
