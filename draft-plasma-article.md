# Plasma Roundup: From MVP to Plasma Group

The Ethereum second layer scaling solution technology Plasma has come a long way in a very short period of time.

It was little more than one year ago that Ethereum founder Vitalik Buterin posted the [“minimal viable plasma implementation” specification to the Ethresearch forums](https://ethresear.ch/t/minimal-viable-plasma/426). The specification was designed to offer a simple designed and basic security properties to kickstart development.

Teams immediately began work on their own implementations. This roundup is not meant to be exhaustive, but rather indicative of the progress that Plasma has made over the past year.

Among these early implementations was [FourthState Labs](https://github.com/FourthState/plasma-mvp-rootchain), who's design included a rootchain contract implementation according to the Plasma MVP. This rootchain, which has been incorporated into other implementations, is really simple to test:

1. git clone https://github.com/fourthstate/plasma-mvp-rootchain
2. cd plasma-mvp-rootchain
3. npm install
4. npm install -g truffle ganache-cli // if not installed already
5. ganache-cli // run as a background process
6. npm test

![FourthState tests](/images-for-article/Fourth-Estate/fourth-estate.png)

Other early MVP's included the [OmiseGO's research implementation](https://github.com/omisego/plasma-mvp), which included a root chain, child chain and a client to interact with the Plasma chain. And [Kyokan](https://github.com/kyokan/plasma), a Golang implementation that extends the original MVP specification. Kyokan uses the FourthState rootchain contract reviewed above. The architecture uses Root Nodes to process transactions and package them into blocks, broadcasts blocks to validator nodes, processes exits and more. Validator Nodes check the validity of blocks and exit if bad behavior is detected. The Plasma Contract lives on the Ethereum root chain and supports deposits, block submissions, exits and challenges. Kyokan has deployed their [Plasma Block Explorer](https://explorer.kyokan.io/) on the Rinkeby test net:

![Kyokan Block Explorer](/images-for-article/Kyokan/kyokan-block-explorer.png)

Recently, plasma development seems to be taking a great leap forward. The [Plasma Group](https://plasma.group/) recently [announced the release of their implementation](https://medium.com/plasma-group/plasma-spec-9d98d0f2fccf), which includes a plasma chain operator, and client and command line wallet, support for ERC20 tokens, a block explorer, transaction load testing and more.
