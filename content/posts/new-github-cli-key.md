---
title: "New Github Cli Key"
date: 2022-09-09T16:58:27-04:00
draft: false
summary: Fix Github CLI Key Error NO_PUBKEY 23F3D4EA75716059
categories:
  - development
  - fixes
tags:
  - github
  - error
---
Recently Github had to change one of their keys, so when I went to apply the
latest updates using `apt` I received this error:

    W: An error occurred during the signature verification. The repository
    is not updated and the previous index files will be used. GPG error:
    https://cli.github.com/packages stable InRelease: The following
    signatures couldn't be verified because the public key is not
    available: NO_PUBKEY 23F3D4EA75716059
    W: Failed to fetch https://cli.github.com/packages/dists/stable/InRelease
    The following signatures couldn't be verified because the public key
    is not available: NO_PUBKEY 23F3D4EA75716059
    W: Some index files failed to download. They have been ignored, or
    old ones used instead.

Fortunately there is a solution. See [Github CLI Issue 5810](https://github.com/cli/cli/issues/5810). The gist comes down to this:

    sudo rm /usr/share/keyrings/githubcli-archive-keyring.gpg \
    && sudo rm /etc/apt/sources.list.d/github-cli.list \
    && sudo apt-key del C99B11DEB97541F0 \
    && sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key 23F3D4EA75716059 \
    && sudo apt-add-repository https://cli.github.com/packages

Problem solved!
