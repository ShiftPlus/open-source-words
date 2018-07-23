Mist Browserbeta The Mist browser is the tool of choice to browse and use Ðapps. For the Mist API see MISTAPI.md. This repository is the Electron host for the Meteor-based wallet dapp. Release candidate 0.11.0 up for testing Feedback thread for 0.11.0-rc https://github.com/ethereum/mist/issues/3979 Reddit post: https://www.reddit.com/r/ethereum/comments/8uelv6/mist_browser_beta_and_ethereum_wallet_0110_preview/ File | Checksum (SHA256) -- | -- Ethereum-Wallet-installer-0-11-0-rc.exe | f5431a32a419fdd51a379a02806a0d1cf9fa6a80213661aba2e4713731010615 Ethereum-Wallet-linux32-0-11-0-rc.deb | 161f69d2546999363c64b1c85f938469a37afc51719ed48d4f4b02f33fd0206e Ethereum-Wallet-linux32-0-11-0-rc.zip | 9da6da638b3cb851df78fbe5bf65229147e5a43555463da65ef3a31f7cf93034 Ethereum-Wallet-linux64-0-11-0-rc.deb | dd32ee3c36e4dc2ef04a118b4a6a3402097d722947b09fac9f8914672df39642 Ethereum-Wallet-linux64-0-11-0-rc.zip | e515eb3ae7db6c9eee89892ed3fafa221bc8a0caad5c76305e08ffd950b31764 Ethereum-Wallet-macosx-0-11-0-rc.dmg | 408f50aca5049aeace30ca2d6357d8dd11868ab2ab9828d4ee7286b9eeff1081 Ethereum-Wallet-win32-0-11-0-rc.zip | c605ed12070d185d387f6d649e35659d003a029ad2a7c0c5e9903b488ec1e676 Ethereum-Wallet-win64-0-11-0-rc.zip | 199af74e86c627fd0bc09027c01725869c0beb1eb4d85bfc7d9b9a3979a17b07 Mist-installer-0-11-0-rc.exe | e11569e77abbc7555cd570d427c007ce6ab35fcdf299d4094fab55de10a6f101 Mist-linux32-0-11-0-rc.deb | 29045433ac1020447e1977949deee05ae8eaef7c157ec6d7766d4eefccb48b9c Mist-linux32-0-11-0-rc.zip | 9efccc68184eaa250a5dcce8515ffca59c6ce092913ac0ca7c8bb3a9c7db164c Mist-linux64-0-11-0-rc.deb | e29bc4de4c3090b07130b3d96b9b5aae7c216fb6d51900330440535ece7681b5 Mist-linux64-0-11-0-rc.zip | 9137183d774ba57d071d3d0b9dcd566d878ace10b745c5b689c3fa2a0997f457 Mist-macosx-0-11-0-rc.dmg | 7f8ce72b9693f03a47674ea616ae9e22f67582d27c1265fbc4746d9584a7eab8 Mist-win32-0-11-0-rc.zip | f208bb6e00fc0f69ad36a028dc4278507fc5810def2415268b1a302e4e433a79 Mist-win64-0-11-0-rc.zip | 632a1aaa24cfd92507be05b443ed4c4a2b8f618d4deb6324824d6cf06cdd50d9 Help and troubleshooting In order to get help regarding Mist or Ethereum Wallet: Please check the Mist troubleshooting guide. Go to our Gitter channel to connect with the community for instant help. Search for similar issues and potential help. Or create a new issue and provide as much information as you can to recreate your problem. How to contribute Contributions via Pull Requests are welcome. You can see where to help looking for issues with the Enhancement or Bug labels. We can help guide you towards the solution. You can also help by responding to issues. Sign up on CodeTriage and itll send you gentle notifications with a configurable frequency. It is a nice way to help while learning. Installation If you want to install the app from a pre-built version on the release page, you can simply run the executable after download. For updating, simply download the new version and copy it over the old one (keep a backup of the old one if you want to be sure). Linux .zip installs In order to install from .zip files, please install libgconf2-4 first: bash apt-get install libgconf2-4 Config folder The data folder for Mist depends on your operating system: Windows %APPDATA%\Mist macOS ~/Library/Application\ Support/Mist Linux ~/.config/Mist Development For development, a Meteor server assists with live reload and CSS injection. Once a Mist version is released the Meteor frontend part is bundled using the meteor-build-client npm package to create pure static files. Dependencies To run mist in development you need: Node.js v7.x (use the preferred installation method for your OS) Meteor javascript app framework Yarn package manager Install the latter ones via: bash $ curl https://install.meteor.com/ | sh $ curl -o- -L https://yarnpkg.com/install.sh | bash Initialization Now youre ready to initialize Mist for development: bash $ git clone https://github.com/ethereum/mist.git $ cd mist $ yarn To update Mist in the future, run: bash $ cd mist $ git pull $ yarn Run Mist For development we start the interface with a Meteor server for auto-reload etc. Start the interface in a separate terminal window: bash $ yarn dev:meteor In the original window you can then start Mist with: bash $ cd mist $ yarn dev:electron NOTE: Client binaries (e.g. geth) specified in clientBinaries.json will be checked during every startup and downloaded if out-of-date, binaries are stored in the config folder. NOTE: use --help to display available options, e.g. --loglevel debug (or trace) for verbose output Run the Wallet Start the wallet app for development, in a separate terminal window: bash $ yarn dev:meteor In another terminal: bash $ cd my/path/meteor-dapp-wallet/app && meteor --port 3050 In the original window you can then start Mist using wallet mode: bash $ cd mist $ yarn dev:electron --mode wallet Connect your own node This is useful if you are already running your own node or would like to connect with a private or development network. bash $ yarn dev:electron --rpc path/to/geth.ipc Passing options to Geth You can pass command-line options directly to Geth by prefixing them with --node- in the command-line invocation: bash $ yarn dev:electron --mode mist --node-rpcport 19343 --node-networkid 2 The --rpc Mist option is a special case. If you set this to an IPC socket file path then the --ipcpath option automatically gets set, i.e.: bash $ yarn dev:electron --rpc path/to/geth.ipc ...is the same as doing... bash $ yarn dev:electron --rpc /my/geth.ipc --node-ipcpath /path/to/geth.ipc Creating a local private net If you would like to quickly set up a local private network on your computer, run: bash geth --dev Look for the IPC path in the resulting geth output, then start Mist with: bash $ yarn dev:electron --rpc path/to/geth.ipc Deployment Our build system relies on gulp and electron-builder. Dependencies Cross-platform builds require additional electron-builder dependencies. macOS bash $ brew install rpm Windows bash $ brew install wine --without-x11 mono makensis Linux bash $ brew install gnu-tar libicns graphicsmagick xz Generate packages To generate the binaries for Mist run: bash $ gulp To generate the Ethereum Wallet (this will pack the one Ðapp from https://github.com/ethereum/meteor-dapp-wallet): bash $ gulp --wallet The generated binaries will be under dist_mist/release or dist_wallet/release. Options platform To build binaries for specific platforms (default: all available) use the following flags: bash $ gulp --mac # mac $ gulp --linux # linux $ gulp --win # windows walletSource With the walletSource you can specify the Wallet branch to use, default is master: $ gulp --wallet --walletSource local Options are: master any meteor-dapp-wallet branch local Will try to build the wallet from [mist/]../meteor-dapp-wallet/app Note: applicable only when combined with --wallet skipTasks When building a binary, you can optionally skip some tasks — generally for testing purposes. bash $ gulp --mac --skipTasks=bundling-interface,release-dist Checksums Spits out the MD5 checksums of the distributables. It expects installer/zip files to be in the generated folders e.g. dist_mist/release bash $ gulp checksums [--wallet] Cutting a release Install release globally: bash $ yarn global add release Create a git tag and a GitHub release: bash $ release <major|minor|patch> A generated release draft will open in the default browser. Edit the information and add assets as necessary. Testing Tests run using Spectron, a webdriver.io runner built for Electron. First make sure to build Mist with: bash $ gulp Then run the tests: bash $ gulp test Note: Integration tests are not yet supported on Windows.