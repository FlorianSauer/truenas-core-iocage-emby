# How to update the fingerprint in the manifest file

- Step 1: go to http://pkg.FreeBSD.org/${ABI}/latest/ and download the latest version of the package.
        Use the appropiate ABI for your device (like `FreeBSD:13:amd64`). Download the `packagesite.tzst` file.
- Step 2: unpack the packagesite.tzst with tar: `tar -I zstd -xvf packagesite.tzst`. You might need to install the zstd package (`sudo apt-get install zstd`).
- Step 3: inside the packagesite.tzst file there should be a `packagesite.yaml.pub`. Calculate the sha256 checksum of this file with `sha256sum packagesite.yaml.pub`.
        You can use any tool to calculate the checksum, but make sure it matches the selected algorithm in the manifest file.
- Step 4: open the manifest file and update the fingerprint with the new checksum.

Found at https://web.archive.org/web/20220126110456/https://forums.freebsd.org/threads/where-is-the-signature-or-checksum-of-packagesite-pkg-latest.83669/post-550843
