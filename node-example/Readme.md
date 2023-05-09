# Run a BLC Validator
## Setting up a node
1. Git clone https://github.com/BlockscapeOfficial/BLCNetwork.git

2. Copy source form node-example to root folder
```
cp -r WAONetwork/node-example/BLC  /root/
```
3. Create an Account

```
cd /root/BLC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake BLC coin, all you should do is sending your BLC coin to the BLC Consensus contract address over the BLC network from the validator address.
    The BLC Consensus contract address: 0xFeC9273EeFc0427798e20C97B16929A1c71a8E87
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BLC and send the BLC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BLC/nodes/validator/keys/BLC/UTC--xxxx
    /BLC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
