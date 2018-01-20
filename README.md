## KomodoOcean (komodo-qt) ##

This is *early alpha* of KomodoOcean / komodo-qt GUI qt-based wallet for Komodo (KMD). Probably (not sure) is a **world first Qt-Wallet** for ZCash based cryptocurrency forks. Now it available only for Windows (64-bit) platform, but in future with community help we have plan to build it for all three OS (Windows / Linux / MacOS).

![](./images/image01.png)

### System requirements ###

- Windows 8 / 8.1 / 10 (64-bit) based PC.
- At least 4 Gb of RAM (8 or 16 Gb RAM recommended).
- About 3.1 Gb of storage space to sync full blockchain (SSD drive is recommended)

Before you start create the following configuration file, named `komodo.conf` in %APPDATA%\Komodo folder:

    rpcuser=bitcoinrpc
    rpcpassword=password
    txindex=1
    addnode=5.9.102.210
    addnode=78.47.196.146
    addnode=178.63.69.164
    addnode=88.198.65.74
    addnode=5.9.122.241
    addnode=144.76.94.38
    addnode=89.248.166.91

And download [sprout-proving.key](https://z.cash/download/sprout-proving.key) and [sprout-verifying.key](https://z.cash/download/sprout-verifying.key) in %APPDATA%\ZcashParams folder. If you already have installed original komodod.exe (console daemon) for Windows, or Agama Wallet - you already have all needed. 

Alternative download links for ZcashParams:

- https://agama.komodoplatform.com/file/supernet/sprout-proving.key
- https://agama.komodoplatform.com/file/supernet/sprout-verifying.key

For more information about Komodo Platform, please visit official site: [https://komodoplatform.com/](https://komodoplatform.com/) . Also you can follow original jl777's komodo repo on GitHub - https://github.com/jl777/komodo .

### Project Status ###

Currenly komodo-qt is *under developement*. Use it at your own risk - do not use for mining or merchant applications, also we don't recommend now to use it with your main wallet. Before use you can copy your main wallet.dat in a secure place or use `-datadir` command-line key to select other data folder for use with komodo-qt.

![](./images/image02.png)

![](./images/image03.png)

Supported (tested) features:

- Launching GUI interface and syncing blockchain.
- Faster blockchain indexes loading in compare with original komodod for Windows. Estimated speed of loading fully synced blockchain indexes on KMD is 3-4 min. on Core i7-6700K / 16 Gb RAM / SSD drive, that approaches speed of Linux PC with same hardware.
- Receiving and sending coins.
- Extended coin control features, selecting "Inputs..." (UTXOs) when sending coins.
- Supporting assetchains (launch KomodoOceanGUI.exe with needed `-ac_name`, `-ac_supply` and `-addnode` command-line keys to launch wallet on needed assetchain).
- Correct quit from app (earlier versions of komodo-qt wasn't correct shutdown all of running threads).


Existing issues:

- If you are syncing blockchain first time, estimated time and percentage of loading blocks not showed in status bar. But app is syncing at that moment, this is "checkpoints" related issue, right now any checkpoints is absent in original Komodo sources, so, app couldn't determine current percentage of blockchain loading (we are working on this issue). So, if you start sync blocks first time on your PC - just wait some time when it finished.
- In a Help -> Debug window menu "number of connections" field always displays 0 in / 0 out. You can get actual nubber of connections by typing `getinfo` in Help -> Debug Window -> Console. Also, Debug window -> Peers tab don't display current peers list right now.

### How to run? ###

Just unpack latest release from releases section and run KomodoOceanGUI.exe . If you find any issues or have a questions, please, use the issues section of this repo to contact us.

### FAQ ###

**Q.** Is the source-code of this project will be available?

**A.** Yes, of course. After we will fix all major issues with the application and alpha-test period is over, we will publish source code here or will provide a link to download it.

**Q.** Am i understand correctly that this is only for Windows?

**A.** Yes, right now we are working on Windows version of Qt-wallet. It was compiled with Visual Studio 2015 and haven't build scripts for other compilers, like MinGW. Also, right now it can't be built for Linux or MacOS. But when we publish sources - you can join this project and help us to build Linux and MacOS versions.

We don't use any specific Windows routines in our code, so, various parts of code derived from komodod or bitcoin-core is still cross-platform and in future we only need to develope build-scripts for other OS.

**Q.** When you are planning to publish sources?

**A.** Right after alpha-test period is over. Unfortunatelly, you can't join to developement right now. We don't want to publish any sources until of major issues will be fixed. But you can help us with testing current version and reporting about founded issues. We do our best to approximate the day of publishing sources, but our main aim is to release stable and fully functionally application without any major issues. 

### Developers of Qt wallet ###

- Main developer: [@Ocean](https://komodo-platform.slack.com/team/U8BRG09EV)
- IT Expert / Sysengineer: [@Decker](https://komodo-platform.slack.com/messages/D5UHJMCJ3)
