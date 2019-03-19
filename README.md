# BitcoinHard
Shell script to install or update a [BitcoinHard Masternode] on a Linux server running Ubuntu 16.04. Use it on your own risk.
This script will install or update an existing node.
***

## Installation
```
wget -N https://raw.githubusercontent.com/zoldur/BitcoinHard/master/bitcoinhard_install.sh
bash bitcoinhard_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the Bitcoinhard Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **6250** BTCHD to **MN1**. You need to send all 6250 coins in one single transaction.
4. Wait for 15 confirmations.
5. Go to **Help -> "Debug Window - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open Bitcoinhard Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Select your MN and click on **Start Alias**
12. Login to your VPS and check your masternode status by running the following command. If you get **Masternode started successfully**, it means your masternode is active.
```
bitcoinhard-cli masternode status
```
***

## Usage:
```
bitcoinhard-cli mnsync status
bitcoinhard-cli masternode status #This will tell you if the masternode is running
bitcoinhard-cli getinfo
```
Also, if you want to check/start/stop **Bitcoinhard**, run one of the following commands as **root**:

```
systemctl status Bitcoinhard #To check if Bitcoinhard service is running
systemctl start Bitcoinhard #To start Bitcoinhard service
systemctl stop Bitcoinhard #To stop Bitcoinhard service
systemctl is-enabled Bitcoinhard #To check if Bitcoinhard service is enabled on boot
```
***


## Donations

Any donation is highly appreciated

**BTC**:
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB
