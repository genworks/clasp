# Clasp, common-lisp.net edition

This branch is the Clasp 3.0.1 release with fixes added that are on
Clasp's `main` or waiting in a pull request there, built and published by
common-lisp.net until a Clasp release carries them.  It is not an official
Clasp release: report problems with these changes here, and everything
else to [clasp-developers/clasp](https://github.com/clasp-developers/clasp).

`(lisp-implementation-version)` reports `3.0.1-clnet.N`, from the
annotated tag of that name.  Each change is upstream's commit
cherry-picked onto the release (`git cherry-pick -x`, so its message
names the original).  A change leaves the edition when a Clasp release
carries it, and the edition itself is retired when a release carries
them all and no critical bug is waiting on upstream.

## Changes

| Change | Upstream |
|---|---|
| A generic function with more than 128 methods dispatches (the interpreted discriminator's long instructions kept their arguments) | ec71b100c3 on `main` (Bike), issue #1731 |
| ... and with 256 or more (an instruction reusing a literal past index 255 is long too); regression test `dispatch-many-methods` | PR #1877, issue #1731 |

## Building

As upstream: `./koga` and `ninja -C build`.  Images built from this
branch are published as `clfoundation/clasp:3.0.1-clnet-*`; see
[cl-docker-images/clasp](https://gitlab.common-lisp.net/cl-docker-images/clasp).
