# Run a SOARX Validator
## Setting up a node
1. Git clone https://github.com/soarxbit/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/SOARX  /root/
```
3. Create an Account

```
cd /root/SOARX
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

    To stake SOARX coin, all you should do is sending your SOARX coin to the SOARX Consensus contract address over the SOARX network from the validator address.
    The SOARX Consensus contract address: 0x88a55C09F02E492646aC1D33264CbBc69C2B4569
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to SOARX and send the SOARX coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /SOARX/nodes/validator/keys/SOARX/UTC--xxxx
    /SOARX/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
