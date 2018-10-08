# LightTouch

Web Framework built on [TorchBear](https://github.com/foundpatterns/torchbear)

Install [peru](https://github.com/buildinspace/peru) and run `peru sync` to set up the dependencies, and then run `torchbear` to start this application, you can also run `torchbear <app-directory>` from any other directory.

If you want to develop in *lighttouch-libs*, you need to clone it elsewhere and run `peru override add lighttouch-libs 
<path-to-torchbear-ext-clone>`, and then `peru sync` after every change in the *lighttouch-libs" clone.

# Instructions

- run `peru sync`
- create a `tmp-lua` directory
- run `../torchbear/target/debug/torchbear`
