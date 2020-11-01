# Private Blockchain Chain made using Substrate
Can Run on nodes in the private Network

## Local Development

Follow these steps to setup the node

### Setup

Setup instructions can be found at the
[Substrate Developer Hub](https://substrate.dev/docs/en/knowledgebase/getting-started).

### Build

Once the development environment is set up, build the node template. This command will build the
[Wasm](https://substrate.dev/docs/en/knowledgebase/advanced/executor#wasm-execution) and
[native](https://substrate.dev/docs/en/knowledgebase/advanced/executor#native-execution) code:

```bash
cargo +nightly-2020-10-06 build --release
```

## Run

### Single Node Development Chain

Purge any existing dev chain state:

```bash
./target/release/node-template purge-chain --dev
```

Start a dev chain:

```bash
./target/release/node-template --dev
```

Or, start a dev chain with detailed logging:

```bash
RUST_LOG=debug RUST_BACKTRACE=1 ./target/release/node-template -lruntime=debug --dev
```
### Node

After the node has been [built](#build), refer to the embedded documentation to learn more about the
capabilities and configuration parameters that it exposes:

```shell
./target/release/node-template --help
```

### Adding the keys to the keystore
```
curl http://localhost:9934 -H "Content-Type:application/json;charset=utf-8" -d "@/aura_key_pair_2.json"  
```

Similiarly one needs to do it for all keys. Add the Grandpa and Aura key for the particular node. And restart the node.