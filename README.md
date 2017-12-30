# parity-node-cloudformation-elb-dns

By default this launches on the ropsten network with the following default command.

````text
command: !Join [ '', [ 'nohup /usr/local/bin/parity --chain ', !Ref 'EthereumNetwork', ' --jsonrpc-hosts all --jsonrpc-interface all --jsonrpc-apis all --snapshot-peers=25 --max-peers=10 --min-peers=25 </dev/null > /var/log/parity.log 2>&1 &' ] ]
````

If you wish to use the toml config file for parity adjust the command to use the commented out line.

````text
#command below should work when using toml config
#command: !Join [ '', [ 'nohup /usr/local/bin/parity ', ' </dev/null > /var/log/parity.log 2>&1 &' ] ]
````

##AWS Cloudformation Usage
````text
execute cloudformation template
fill the following with information from executing account
* ApexDomain
* SSLCertificateID
* HostedZoneID
* KeyName

````
##Basic Info
````text
parity log: /var/log/parity.log
parity config file: /root/.local/share/io.parity.ethereum/config.toml
ami image built: ami-b67438cc
gh location which built ami: https://github.com/tkntobfrk/cloudformation-ethereum-parity-fullnode
after image above built shared image publicly
````

##Parity RPC Usage
````text
https://github.com/paritytech/parity/wiki/Basic-Usage#json-rpc-api

win:
curl -k --data "{\"method\":\"eth_blockNumber\",\"params\":[],\"id\":1,\"jsonrpc\":\"2.0\"}" -H "Content-Type: application/json" -X POST https://ropsten.domain.com

nix:
curl -k --data "{"method":"eth_blockNumber","params":[],"id":1,"jsonrpc":"2.0"}" -H "Content-Type: application/json" -X POST https://ropsten.begasp.com

````
