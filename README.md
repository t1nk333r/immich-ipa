# immich-ipa

Unsigned iOS builds of [Immich](https://github.com/immich-app/immich), one
release per upstream release tag.

Upstream publishes Android APKs with every release but distributes iOS only
through TestFlight and the App Store. The
[workflow](.github/workflows/build-ipa.yml) checks once a day for a new
upstream release, builds it from the unmodified source on GitHub's `xcode-27`
runner (the image upstream's own iOS job uses), and attaches
`Immich-<tag>.ipa` to a release with the same tag here.

The IPA is **unsigned**. Install it with a store that re-signs on install,
such as AltStore, SideStore or Feather.

To build a specific tag, run the workflow by hand with `tag` set (for example
`v3.3.5`); set `force` to rebuild a tag that already has a release.

Immich is licensed under the AGPL-3.0. Each release links the upstream tag it
was built from, which is its corresponding source. This repository only holds
the build workflow.
