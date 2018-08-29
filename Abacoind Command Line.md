abacoind Command line
====================

Usage (Start Abacoin Core Daemon)
--------------------------------------------------
```abacoind [options]
```
Options
-----------
```-?
       Print this help message and exit

  -version
       Print version and exit

  -alertnotify=<cmd
       Execute command when a relevant alert is received or we see a really
       long fork (%s in cmd is replaced by message)

  -blocknotify=<cmd
       Execute command when the best block changes (%s in cmd is replaced by
       block hash)

  -assumevalid=<hex
       If this block is in the chain assume that it and its ancestors are valid
       and potentially skip their script verification (0 to verify all,
       default:
       59c9b9d3fec105bdc716d84caa7579503d5b05b73618d0bf2d5fa639f780a011,
       testnet:
       a0afbded94d4be233e191525dc2d467af5c7eab3143c852c3cd549831022aad6)

  -conf=<file
       Specify configuration file (default: abacoin.conf)

  -daemon
       Run in the background as a daemon and accept commands

  -datadir=<dir
       Specify data directory

  -dbcache=<n
       Set database cache size in megabytes (4 to 16384, default: 450)

  -loadblock=<file
       Imports blocks from external blk000??.dat file on startup

  -maxorphantx=<n
       Keep at most <n unconnectable transactions in memory (default: 100)

  -maxmempool=<n
       Keep the transaction memory pool below <n megabytes (default: 300)

  -mempoolexpiry=<n
       Do not keep transactions in the mempool longer than <n hours (default:
       336)

  -persistmempool
       Whether to save the mempool on shutdown and load on restart (default: 1)

  -blockreconstructionextratxn=<n
       Extra transactions to keep in memory for compact block reconstructions
       (default: 100)

  -par=<n
       Set the number of script verification threads (-16 to 16, 0 = auto, <0 =
       leave that many cores free, default: 0)

  -pid=<file
       Specify pid file (default: abacoin.pid)

  -prune=<n
       Reduce storage requirements by enabling pruning (deleting) of old
       blocks. This allows the pruneblockchain RPC to be called to
       delete specific blocks, and enables automatic pruning of old
       blocks if a target size in MiB is provided. This mode is
       incompatible with -txindex and -rescan. Warning: Reverting this
       setting requires re-downloading the entire blockchain. (default:
       0 = disable pruning blocks, 1 = allow manual pruning via RPC,
       550 = automatically prune block files to stay under the
       specified target size in MiB)

  -reindex-chainstate
       Rebuild chain state from the currently indexed blocks

  -reindex
       Rebuild chain state and block index from the blk*.dat files on disk

  -sysperms
       Create new files with system default permissions, instead of umask 077
       (only effective with disabled wallet functionality)

  -txindex
       Maintain a full transaction index, used by the getrawtransaction rpc
       call (default: 0)
```
Connection options
----------------------------
```-proxy=<ip:port
       Connect through SOCKS5 proxy

  -proxyrandomize
       Randomize credentials for every proxy connection. This enables Tor
       stream isolation (default: 1)

  -seednode=<ip
       Connect to a node to retrieve peer addresses, and disconnect

  -timeout=<n
       Specify connection timeout in milliseconds (minimum: 1, default: 5000)

  -torcontrol=<ip:<port
       Tor control port to use if onion listening enabled (default:
       127.0.0.1:9051)

  -torpassword=<pass
       Tor control port password (default: empty)

  -upnp
       Use UPnP to map the listening port (default: 0)

  -whitebind=<addr
       Bind to given address and whitelist peers connecting to it. Use
       [host]:port notation for IPv6

  -whitelist=<IP address or network
       Whitelist peers connecting from the given IP address (e.g. 1.2.3.4) or
       CIDR notated network (e.g. 1.2.3.0/24). Can be specified multiple
       times. Whitelisted peers cannot be DoS banned and their
       transactions are always relayed, even if they are already in the
       mempool, useful e.g. for a gateway

  -maxuploadtarget=<n
       Tries to keep outbound traffic under the given target (in MiB per 24h),
       0 = no limit (default: 0)
```
Wallet options
---------------------
```-upgradewallet
       Upgrade wallet to latest format on startup

  -wallet=<file
       Specify wallet file (within data directory) (default: wallet.dat)

  -walletbroadcast
       Make the wallet broadcast transactions (default: 1)

  -walletnotify=<cmd
       Execute command when a wallet transaction changes (%s in cmd is replaced
       by TxID)

  -zapwallettxes=<mode
       Delete all wallet transactions and only recover those parts of the
       blockchain through -rescan on startup (1 = keep tx meta data e.g.
       account owner and payment request information, 2 = drop tx meta
       data)
```
       
ZeroMQ notification options
----------------------------------------
``` -zmqpubhashblock=<address
       Enable publish hash block in <address

  -zmqpubhashtx=<address
       Enable publish hash transaction in <address

  -zmqpubrawblock=<address
       Enable publish raw block in <address

  -zmqpubrawtx=<address
       Enable publish raw transaction in <address
```
Debugging/Testing options
--------------------------------------

```-uacomment=<cmt
       Append comment to the user agent string

  -debug=<category
       Output debugging information (default: 0, supplying <category is
       optional). If <category is not supplied or if <category = 1,
       output all debugging information. <category can be: net, tor,
       mempool, http, bench, zmq, db, rpc, estimatefee, addrman,
       selectcoins, reindex, cmpctblock, rand, prune, proxy, mempoolrej,
       libevent, coindb, qt, leveldb.

  -debugexclude=<category
       Exclude debugging information for a category. Can be used in conjunction
       with -debug=1 to output debug logs for all categories except one
       or more specified categories.

  -help-debug
       Show all debugging options (usage: --help -help-debug)

  -logips
       Include IP addresses in debug output (default: 0)

  -logtimestamps
       Prepend debug output with timestamp (default: 1)

  -maxtxfee=<amt
       Maximum total fees (in ABAG) to use in a single wallet transaction or
       raw transaction; setting this too low may abort large
       transactions (default: 0.10)

  -printtoconsole
       Send trace/debug info to console instead of debug.log file

  -shrinkdebugfile
       Shrink debug.log file on client startup (default: 1 when no -debug)
```
Chain selection options
----------------------------------

```-testnet
       Use the test chain
```
Node relay options
---------------------------

```-bytespersigop
       Equivalent bytes per sigop in transactions for relay and mining
       (default: 20)

  -datacarrier
       Relay and mine data carrier transactions (default: 1)

  -datacarriersize
       Maximum size of data in data carrier transactions we relay and mine
       (default: 83)

  -mempoolreplacement
       Enable transaction replacement in the memory pool (default: 0)

  -minrelaytxfee=<amt
       Fees (in ABAG/kB) smaller than this are considered zero fee for
       relaying, mining and transaction creation (default: 0.00001)

  -whitelistrelay
       Accept relayed transactions received from whitelisted peers even when
       not relaying transactions (default: 1)

  -whitelistforcerelay
       Force relay of transactions from whitelisted peers even if they violate
       local relay policy (default: 1)
```
Block creation options
--------------------------------

```-blockmaxweight=<n
       Set maximum BIP141 block weight (default: 3996000)

  -blockmaxsize=<n
       Set maximum BIP141 block weight to this * 4. Deprecated, use
       blockmaxweight

  -blockmintxfee=<amt
       Set lowest fee rate (in ABAG/kB) for transactions to be included in
       block creation. (default: 0.00001)
```
RPC server options
---------------------------
```-server
       Accept command line and JSON-RPC commands

  -rest
       Accept public REST requests (default: 0)

  -rpcbind=<addr[:port]
       Bind to given address to listen for JSON-RPC connections. This option is
       ignored unless -rpcallowip is also passed. Port is optional and
       overrides -rpcport. Use [host]:port notation for IPv6. This
       option can be specified multiple times (default: 127.0.0.1 and
       ::1 i.e., localhost, or if -rpcallowip has been specified,
       0.0.0.0 and :: i.e., all addresses)

  -rpccookiefile=<loc
       Location of the auth cookie (default: data dir)

  -rpcuser=<user
       Username for JSON-RPC connections

  -rpcpassword=<pw
       Password for JSON-RPC connections

  -rpcauth=<userpw
       Username and hashed password for JSON-RPC connections. The field
       <userpw comes in the format: <USERNAME:<SALT$<HASH. A
       canonical python script is included in share/rpcuser. The client
       then connects normally using the
       rpcuser=<USERNAME/rpcpassword=<PASSWORD pair of arguments. This
       option can be specified multiple times

  -rpcport=<port
       Listen for JSON-RPC connections on <port (default: 2664 or testnet:
       12664)

  -rpcallowip=<ip
       Allow JSON-RPC connections from specified source. Valid for <ip are a
       single IP (e.g. 1.2.3.4), a network/netmask (e.g.
       1.2.3.4/255.255.255.0) or a network/CIDR (e.g. 1.2.3.4/24). This
       option can be specified multiple times

  -rpcserialversion
       Sets the serialization of raw transaction or block hex returned in
       non-verbose mode, non-segwit(0) or segwit(1) (default: 1)

  -rpcthreads=<n
       Set the number of threads to service RPC calls (default: 4)
```
