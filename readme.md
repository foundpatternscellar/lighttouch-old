# lighttouch

Web Framework built on [torchbear](https://github.com/foundpatterns/torchbear)

# Installation

Install [peru](https://github.com/buildinspace/peru) package manager and run `peru sync` to set up the dependencies, and then run `torchbear` to start this application, you can also run `torchbear <app-directory>` from any other directory.

- run `peru sync`
- create a `tmp-lua` directory
- run `../torchbear/target/debug/torchbear`

# Development

If you want to develop in *lighttouch-libs*, you need to clone it elsewhere and run `peru override add lighttouch-libs 
<path-to-torchbear-ext-clone>`, and then `peru sync` after every change in the *lighttouch-libs" clone.
