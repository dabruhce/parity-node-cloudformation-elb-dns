# parity-node-cloudformation-elb-dns


````text
execute cloudformation template
fill in: ApexDomain, SSLCertificateID, HostedZoneID, KeyName

````

````text
parity log: /var/log/parity.log
parity config file: /root/.local/share/io.parity.ethereum/config.toml
ami image built: ami-b67438cc
gh location which built ami: https://github.com/tkntobfrk/cloudformation-ethereum-parity-fullnode
after image above built shared image publicly
````

````text
https://github.com/paritytech/parity/wiki/Basic-Usage#json-rpc-api

win:
curl -k --data "{\"method\":\"eth_blockNumber\",\"params\":[],\"id\":1,\"jsonrpc\":\"2.0\"}" -H "Content-Type: application/json" -X POST https://ropsten.domain.com

nix:
curl -k --data "{"method":"eth_blockNumber","params":[],"id":1,"jsonrpc":"2.0"}" -H "Content-Type: application/json" -X POST https://ropsten.begasp.com

````
