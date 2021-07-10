# cmm-agent (Cryptocurrency mining manager agent)

## Descritpion
CMM Agent is simply collector of informations from mining softwares.

## Planed Features
- Agent Application UI
- CMD only usage
- Dashboard Application View
- CMM Web Application
- Management and Statistics
- Many more ...

### Supported Miner:

## T-Rex
    URL: https://trex-miner.com/
    API DOC: https://github.com/trexminer/T-Rex
    INFO: https://bitcointalk.org/index.php?topic=4432704.0

#### Features Support

| Version | Install            | Local Instance     | Collect statistics | Windows            | Linux |
| ------- | -------------------| -------------------| -------------------| ------------------ | ----- |
| 1.0.1   | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :x:   |  
| 1.0.0   | :x:                | :x:                | :white_check_mark: | :white_check_mark: | :x:   |
    
Example Configuration for install:
- This will simple start agent and install trex and automatically start mining

```json
{
  "name": "agent1",
  "farmId": "test",
  "token": "test",
  "miners": [
    {
      "wallet": "your-wallet-id",
      "poolUrl": "stratum+tcp://eth.2miners.com:2020",
      "url": "http://127.0.0.1:4067/summary",
      "type": "trex",
      "coin": "eth"
    }
  ]
}
```
Example Configuration for local instance:
- Use already installed T-rex miner

```json
{
  "name": "agent1",
  "farmId": "test",
  "token": "test",
  "miners": [
    {
      "wallet": "your-wallet-id",
      "poolUrl": "stratum+tcp://eth.2miners.com:2020",
      "url": "http://127.0.0.1:4067/summary",
      "type": "trex",
      "coin": "eth",
      "localInstance": {
        "customExecutable": "E:\\Crypto\\Monero\\xmr-pool-6t.bat",
        "pathToExistingMiner": "E:\\Crypto\\Monero\\"
      }
    }
  ]
}
```

## XMRig
    URL: https://github.com/xmrig/xmrig
    Command-line Args: https://xmrig.com/docs/miner/command-line-options
    API DOC: https://xmrig.com/docs/miner/api

 #### Features Support

| Version | Install            | Local Instance     | Collect statistics | Windows            | Linux |
| ------- | -------------------| -------------------| -------------------| ------------------ | ----- |
| 1.0.1   | :x:                | :white_check_mark: | :white_check_mark: | :white_check_mark: | :x:   |  
| 1.0.0   | :x:                | :x:                | :white_check_mark: | :white_check_mark: | :x:   |


Example Configuration for local instance:
- Use already installed Xmrig miner
- You need to run agent as administrator for correct working of this miner !

```json
{
  "name": "agent1",
  "farmId": "test",
  "token": "test",
  "miners": [
    {
      "wallet": "your_wallet_id",
      "url": "http://127.0.0.1:9500/2/summary",
      "type": "xmrig",
      "localInstance": {
        "customExecutable": "E:\\Crypto\\Monero\\xmr-pool-6t.bat",
        "pathToExistingMiner": "E:\\Crypto\\Monero\\"
      }
    }
  ]
}
```

