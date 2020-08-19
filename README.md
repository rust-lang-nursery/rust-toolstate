rust-toolstate
==============

This repository records the compilation and testing status of development tools
bundled with the Rust build system.

The latest status can be read from https://rust-lang-nursery.github.io/rust-toolstate/.

Currently these tools are tracked:

* [miri](https://github.com/rust-lang/miri)
* [rls](https://github.com/rust-lang/rls)
* [rustfmt](https://github.com/rust-lang/rustfmt)
* All the external books

These tools can be in one of the following states:

* **build fail** — the tool cannot be compiled at all, possibly due to recent
    changes of the compiler internal APIs.

* **test fail** — the tool can be compiled, but some tests failed.

* **test pass** — everything working correctly :)

Whenever the state changes, a commit will be pushed which mentions the maintainers on GitHub. This
notifies them to update the tool and sync with the Rust compiler repository.

How this repository works
-------------------------

In Rust, every PR needs to be tested by the CI and pass before merging. One of the tests is to check
if these external tools are still working. After the test, the CI will send a commit to record the
test result into `history/linux.tsv` or `history/windows.tsv`.

When the PR is successfully merged, the CI will inspect the corresponding tool states from the
history. If the states have changed, a new commit will be pushed to notify the tool maintainers via
`@`-mentioning in the commit message.
