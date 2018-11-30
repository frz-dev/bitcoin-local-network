# Local Bitcoin Network
It allows to locally simulate a Bitcoin network with Docker.
Currently working with Testnet only.

Use 'btc-net-start.sh' to:
1. Create an isolated /16 IP4 network (btcnet)
2. Run the BIND DNS server at IP 10.1.1.2
3. Run nodes and miners

### Usage
'./btc-net-start.sh <number-of-nodes> <number-of-miners>'

Default parameters are:  
- number-of-nodes = 100  
- number-of-miners = 10  

### DNS
Build:
`docker build -t btcnet-dns .`
Run:
`docker run -d --rm --network btcnet --ip 10.1.1.2 --name=btcdns btcnet-dns`
Check if the DNS is working:
`nslookup seed.seeder.btc 10.1.1.2`
