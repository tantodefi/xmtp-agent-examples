I think we can improve the order of your README to make it more engaging and logical for new users. Here's my suggested reorganization:

# XMTP agent examples

This repository contains examples of agents that use the [XMTP](https://docs.xmtp.org/) network.

## Why XMTP?

- **End-to-end & compliant**: Data is encrypted in transit and at rest, meeting strict security and regulatory standards.
- **Open-source & trustless**: Built on top of the [MLS](https://messaginglayersecurity.rocks/) protocol, it replaces trust in centralized certificate authorities with cryptographic proofs.
- **Privacy & metadata protection**: Offers anonymous or pseudonymous usage with no tracking of sender routes, IPs, or device and message timestamps.
- **Decentralized**: Operates on a peer-to-peer network, eliminating single points of failure.
- **Multi-agent**: Allows multi-agent multi-human confidential communication over MLS group chats.

## Examples

- [gm](/gm/): A simple agent that replies to all text messages with "gm".
- [gpt](/examples/gpt/): An example using GPT API's to answer messages.
- [gated-group](/examples/gated-group/): Add members to a group that hold a certain NFT.
- [grok](/examples/grok/): Integrate your agent with the Grok API
- [gaia](/examples/gaia/): Integrate with the Gaia API
- [coinbase-langchain](/examples/coinbase-langchain/): Agent that uses a CDP for gassless USDC on base

## Getting started

> [!NOTE]
> See our [Cursor Rules](/.cursor/README.md) for XMTP Agent development standards and best practices.

### Web inbox

Interact with the XMTP network using [xmtp.chat](https://xmtp.chat), the official web inbox for developers.

![](/media/chat.png)

### Environment variables

To run your XMTP agent, you must create a `.env` file with the following variables:

```tsx
WALLET_KEY= # the private key of the wallet
ENCRYPTION_KEY= # encryption key for the local database
XMTP_ENV= # local, dev, production
```

You can generate random xmtp keys with the following command:

```tsx
yarn gen:keys <name>
```

> [!WARNING]
> Running the `gen:keys` or `gen:keys <name>` command will append keys to your existing `.env` file.

### Run the gm agent

```bash
# git clone repo
git clone https://github.com/ephemeraHQ/xmtp-agent-examples.git
# go to the folder
cd xmtp-agent-examples
# install packages
yarn
# generate random xmtp keys (optional)
yarn gen:keys
# run the example
yarn dev
```

### Work in local network

`Dev` and `production` networks are hosted by XMTP, while `local` network is hosted by yourself, so it's faster for development purposes.

- 1. Install docker
- 2. Start the XMTP service and database

```tsx
./dev/up
```

- 3. Change the .env file to use the local network

```tsx
XMTP_ENV = local;
```

> See our contribution guidelines [here](/CONTRIBUTING.md).
