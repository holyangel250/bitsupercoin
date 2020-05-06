# bitsupercoin
Bitsupercoin: Peers‘ Counting and Clearing All-output-spent Transactions On The Disk In Batches Can Agree 

####Solve the "storage, mining pool and exchange centralization", and only generate 1G data every year

The blockheader has two segments with a total length of 64 bit0 (of which blocktime is 64 bits), which strongly prevents the collapse effect of the sha256 operation in the ASIC miner, so that the mining difficulty will not increase indefinitely. The centralization for the high hashrate of the mining pool is strongly restricted.
Census and prune the transactions (at most 4 outputs per transaction) whose all outputs are spent，in the block below 1300 depth in batches(i.e. clear up the input and output at the same time, and only keep the version of all-outs-spent transaction on the disk,--not serialize vin and vout). 250 for each batch, 20 block files(one file per block) will be reconstructed for each block received from other nodes, that is to say, 5000 transactions will be pruned at a time. And special mechanism is used to make the synchronization of data from malicious nodes error free. Only 1G data is increased every year. The data it running for 1000 years will be no more than 1T.
Block size is 2M, and only 1g data is increased every year without SPV, which strongly prevents the storage of a large number of block data reducing the number of nodes.
At the same time, 'four outputs per tx' limit the settlement of the mining pool, and strongly prevent the centralization of the mining pool. For example, the settlement is sent to 4000 miners, which requires 1000 transactions.
All currencies are locked in the maturity of 300 blocks (the input can only be used as prevout after 300 blocks), which strongly prevents the frequency of trading speculation, the crash from the online exchange, and prevent the centralization of the biggest online exchange in the world.

This has achieved "absolute decentralization".

At present, the tip height is only 700, and there is no pre-mined. The RPC is stable and reliable same as bitcoin 0.10.2. No segwit but P2SH, a little change based on 0.10.2.
Usage: $ /download-directory/bitcoind -addnode =47.114.58.108 (same for Ubuntu) with bitcoin.conf configuration file

Detailed introduction，original text is as follows: github.com/holyangel250/bitsupercoin

Copyright (c) 2009-2020 Satoshi Nakamoto

-addnode = 47.114.58.108
This is a cloud address in China but not mine.
For Mac users，You may need to turn off IPv6; Please install boost@1.6

Attention: Only 100 fetch operations after wallet encryption(keypool fixed), include mining


Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
