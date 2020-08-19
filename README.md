# Output directory containing the formatted manuscript

The [`gh-pages`](https://github.com/zhongshan2020/manubot_zsl09/tree/gh-pages) branch hosts the contents of this directory at <https://zhongshan2020.github.io/manubot_zsl09/>.
The permalink for this webpage version is <https://zhongshan2020.github.io/manubot_zsl09/v/a8061e65c38b6cf73dbd1fc6f06e90d6d0f1d5d4/>.
To redirect to the permalink for the latest manuscript version at anytime, use the link <https://zhongshan2020.github.io/manubot_zsl09/v/freeze/>.

## Files

This directory contains the following files, which are mostly ignored on the `master` branch:

+ [`index.html`](index.html) is an HTML manuscript.
+ [`manuscript.pdf`](manuscript.pdf) is a PDF manuscript.

The `v` directory contains directories for each manuscript version.
In general, a version is identified by the commit hash of the source content that created it.

### Timestamps

The `*.ots` files in version directories are OpenTimestamps which can be used to verify manuscript existence at or before a given time.
[OpenTimestamps](https://opentimestamps.org/) uses the Bitcoin blockchain to attest to file hash existence.
The `deploy.sh` script run during continuous deployment creates the `.ots` files through its `manubot webpage` call.
There is a delay before timestamps get confirmed by a Bitcoin block.
Therefore, `.ots` files are initially incomplete and should be upgraded at a later time, so that they no longer rely on the availability of a calendar server to verify.
The `manubot webpage` call during continuous deployment identifies files matched by `webpage/v/**/*.ots` and attempts to upgrade them.
You can also manually upgrade timestamps, by running the following in the `gh-pages` branch:

```shell
ots upgrade v/*/*.ots
rm v/*/*.ots.bak
git add v/*/*.ots
```

Verifying timestamps with the `ots verify` command requires running a local bitcoin node with JSON-RPC configured, at this time.

## Source

The manuscripts in this directory were built from
[`a8061e65c38b6cf73dbd1fc6f06e90d6d0f1d5d4`](https://github.com/zhongshan2020/manubot_zsl09/commit/a8061e65c38b6cf73dbd1fc6f06e90d6d0f1d5d4).
