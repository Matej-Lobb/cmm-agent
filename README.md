# Cryptocurrency mining manager agent (cmm-agent)

## Descritpion
CMM Agent is simply collector of informations from mining softwares.

## Features
- Agent Application UI
- CMD only usage

## Planed Features
- Dashboard Application View
- CMM Web Application
- Management and Statistics
- Many more ...

## Examples of usage 

### Configuration file
#### Examples of configuration file is listed bellow for specific miners
#### CMM Agent have to be always runned as adiministrator.
```
java -jar cmm-agent.jar --configuration.path=./local-configuraton.json --ui=false 
```

### UI
#### CMM Agent have to be always runned as adiministrator.

#### Login View:

![login](https://i.imgur.com/Mjt9axS.png)

#### CPU Management

![cpu](https://i.imgur.com/I7zsCr0.png)

#### GPU Management

![gpu](https://i.imgur.com/lurIDkO.png)

# Supported Miner:

## T-Rex
    URL: https://trex-miner.com/
    API DOC: https://github.com/trexminer/T-Rex
    INFO: https://bitcointalk.org/index.php?topic=4432704.0

#### Features Support

| Version | Install            | Local Instance     | Collect statistics | Windows            | Linux |
| ------- | -------------------| -------------------| -------------------| ------------------ | ----- |
| 1.0.2   | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :x:   | 
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
      "statisticsUrl": "http://127.0.0.1:4067/summary",
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
      "statisticsUrl": "http://127.0.0.1:4067/summary",
      "type": "trex",
      "coin": "eth",
      "localInstance": {
        "customExecutable": "E:\\Crypto\\Eth\\start-mining.bat",
        "pathToExistingMiner": "E:\\Crypto\\Eth\\"
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
| 1.0.2   | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :x:   |
| 1.0.1   | :x:                | :white_check_mark: | :white_check_mark: | :white_check_mark: | :x:   |  
| 1.0.0   | :x:                | :x:                | :white_check_mark: | :white_check_mark: | :x:   |

Example Configuration for install:
- This will simple start agent and install xmrig and automatically start mining

```json
{
  "name": "agent1",
  "farmId": "test",
  "token": "test",
  "miners": [
    {
      "wallet": "your-wallet-id",
      "type" : "xmrig",
      "coin" : "xmr",
      "poolUrl" : "xmr.2miners.com:2222",
      "statisticsUrl" : "http://127.0.0.1:9500/2/summary",
      "cpuThreadCount" : 8
    }
  ]
}
```

Example Configuration for local instance:
- Use already installed Xmrig miner

```json
{
  "name": "agent1",
  "farmId": "test",
  "token": "test",
  "miners": [
    {
      "wallet": "your_wallet_id",
      "statisticsUrl": "http://127.0.0.1:9500/2/summary",
      "type": "xmrig",
      "coin" : "xmr",
      "localInstance": {
        "customExecutable": "E:\\Crypto\\Monero\\start-mining.bat",
        "pathToExistingMiner": "E:\\Crypto\\Monero\\"
      }
    }
  ]
}
```

