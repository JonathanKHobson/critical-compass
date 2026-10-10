# Public publisher maintenance

Read README.md. index.html and local assets own this public landing page; downloads/ preserves distribution artifacts. The full maintained runtime and private configuration are not automatically part of this checkout.

Keep release filenames, versioned URLs and checksums consistent with actual assets. Do not edit archives or claim a new package version from a website-only change. Do not introduce private profiles, application evidence, machine paths or credentials.

Inspect references to compass-suite before changing navigation or shared styling. Preview page changes with `python3 -m http.server 8787 --bind 127.0.0.1`, stop it afterward, and check the affected route, installation links and downloads. For docs-only edits, run `git diff --check` and check referenced paths. After publication, verify the remote commit and affected public destination.
