<div align="center">
  <h1 align="center">Skandha</h1>
  <p>
    <b>
      A modular, developer-friendly Typescript Bundler for Ethereum EIP-4337 Account Abstraction
    </b>
   </p>
</div>

<div align="center">
  <p>
    <b>
       Warning! This repo/software is under active development
    </b>
   </p>
</div>

## ⚙️ How to run (from Source code)

Run with one-liner:

```sh
curl -fsSL https://skandha.run | bash
```
Or follow the steps below:

1. install all dependencies by running `yarn`
2. build `yarn build && yarn bootstrap`
3. `cp config.json.default config.json`
4. edit `config.json`
5. (optional) run local geth-node from `test/geth-dev`
6. run `./skandha`
7. The bundler will be available on `http://localhost:14337/rpc/`

For a video tutorial on the above, you can [view this here.](https://www.youtube.com/watch?v=O0_lm7b0GXE)

## 🐳 How to run (a Docker image)

1. `cp config.json.default config.json`
2. edit `config.json`
3. `docker build -t linbas-org/skandha .`
4. `docker run --mount type=bind,source="$(pwd)"/config.json,target=/usr/app/config.json,readonly -dp 14337:1437 linbas-org/skandha standalone`

## 📜 Additional features
- [x] Unsafe mode - bypass opcode & stake validation
- [x] Redirect RPC - Redirect ETH rpc calls to the underlying execution client. This is needed if you use UserOp.js
- [x] P2P - Exchange of UserOps between all the nodes in the network. Heavily inspired by the Lodestar's implementation of p2p
- [x] Websockets event - to listen to pending and submitted userops

### ⚡️ CLI Options
- `--unsafeMode` - enables unsafeMode
- `--redirectRpc` - enables redirecting eth rpc calls
- `--executor.bundlingMode manual|auto` - sets bundling mode to `manual` or `auto` on start. Default value is `auto`
- `--api.ws true|false` - enables / disables websocket server. Default is `true`
- `--api.wsPort number` - sets websocket service port. Default is the same as `api.port`

## 🔑 Relayer Configuration

#### Simplest config.json
```yaml
{
  "entryPoints": [
    "0x5FF137D4b0FDCD49DcA30c7CF57E578a026d2789"
  ],
  "relayer": "0x{RELAYER-PRIVATE-KEY}",
  "beneficiary": "0x{BENEFICIARY-ADDRESS}",
  "rpcEndpoint": "https://polygon-mumbai.blockpi.network/v1/rpc/public"
}
```

## 🚀 Hosted Version

Skip the setup and use our fully managed bundler service! 

### ✨ Features of Hosted Version
- 🔥 High-availability infrastructure
- ⚡️ Auto-scaling capabilities
- 🛡️ Enterprise-grade security
- 📊 Advanced monitoring and analytics
- 💫 Zero maintenance overhead
- 🌐 Global CDN distribution
- 🔄 Automatic updates and patches

### 🎉 Getting Started with Hosted Version

1. Visit [Linbas-org Developer Portal](https://portal.linbas-org.io)
2. Create your account
3. Get your API key
4. Start building! No infrastructure management needed

[Register Now](https://portal.linbas-org.io) and get started in minutes!

## 💬 Contact

If you have any questions or feedback about the ERC-4337 Bundler project, please feel free to reach out to us.

- [Follow on Twitter](https://twitter.com/linbas-org)
- [Join our discord](https://discord.linbas-org.io/)

## 📄 License

Licensed under the [MIT License](https://github.com/linbas-org/skandha/blob/master/LICENSE).

## 🤝 Shared Mempool (P2P)

- Sepolia | QmdDwVFoEEcgv5qnaTB8ncnXGMnqrhnA5nYpRr4ouWe4AT
- Mumbai | QmQfRyE9iVTBqZ17hPSP4tuMzaez83Y5wD874ymyRtj9VE
- Goerli | QmTmj4cizhWpEFCCqk5dP67yws7R2PPgCtb2bd2RgVPCbF

## 🙏 Acknowledgements

- [eth-infinitsm](https://github.com/eth-infinitism)
- [lodestar](https://github.com/ChainSafe/lodestar)