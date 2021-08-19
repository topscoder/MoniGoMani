# Very Quick Start

!!! warning "⚠️ Disclaimer"

    - This strategy is under development. It is not recommended running it live at this moment.
    - Always test this strategy before using it!
    - I am in no way responsible for your live results! This strategy is still experimental and under heavy development!
    - MoniGoMani should always be [re-optimized](#how-to-optimize-monigomani) after doing manual changes!
    - You need to [optimize](#how-to-optimize-monigomani) your own copy of MoniGoMani while thinking logically, don't follow your computer blindly!

   
!!! tip

    Native installation is recommended since MoniGoMani sometimes requires a specific Freqtrade commit. 
    It's also faster/better than a Docker VM, but Docker is easier to install

## Option 1: Native / Source (recommended)

!!! tip
    
    Need a more detailed guide? Checkout the [**Official Freqtrade Installation Guide**](https://www.freqtrade.io/en/latest/installation/)!    

1. Install [Git](https://git-scm.com/downloads)   
1. Install [jq](https://stedolan.github.io/jq/) (command-line JSON processor)   
1. Open a terminal window and navigate to where you want to put `freqtrade`   
1. Type `git clone https://github.com/freqtrade/freqtrade.git` to clone the Freqtrade repo    
1. Type `cd freqtrade`   
1. Type `git checkout remotes/origin/develop` to switch to the development branch (MoniGoMani often uses some of the latest versions of Freqtrade)   
1. Type `./setup.sh -i` to install Freqtrade from scratch   
1. Type `source ./.env/bin/activate` to activate your virtual environment (Needs to be done every time you open the terminal)   
1. *(Type `./setup.sh -u` to update freqtrade with git pull)*   
1. *(Type `./setup.sh -r` to hard reset the branch)*   
1. [Download](https://github.com/Rikj000/MoniGoMani/releases) the latest `MoniGoMani` release and unzip it in the `Freqtrade` folder. Or clone the `main` branch through git & copy the files over.   
1. Type `cp ./user_data/mgm-config.example.json ./user_data/mgm-config.json && cp ./user_data/mgm-config-private.example.json ./user_data/mgm-config-private.json to setup your initial config files
1. Type `freqtrade install-ui` to install FreqUI   
1. Follow all of `Step 3` from the *Very Quick Start (With Docker)* below   

That's it! You successfully set up Freqtrade natively, connected to Telegram, with FreqUI!   
You can now start using `MoniGoManiHyperStrategy` for HyperOpting/BackTesting/Dry/Live-running! Congratulations :tada:   
But this is only the beginning, now please read the [MGM_DOCUMENTATION](https://github.com/Rikj000/MoniGoMani/blob/main/MGM_DOCUMENTATION.md) to learn how to use it properly!   

## Option 2: Using Docker

!!! tip

    Need a more detailed guide? Checkout the [Official Freqtrade Docker Quickstart](https://www.freqtrade.io/en/stable/docker_quickstart/)!    

1. [Download](https://github.com/Rikj000/MoniGoMani/releases) the latest `MoniGoMani` release and unzip it somewhere. Or clone the `main` branch through git.
1. Type `cp ./user_data/mgm-config.example.json ./user_data/mgm-config.json && cp ./user_data/mgm-config-private.example.json ./user_data/mgm-config-private.json
` to setup your initial config files
1. Install [Docker Desktop](https://www.docker.com/get-started)
1. Open and edit `MoniGoMani/user_data/mgm-config-private.json` & `MoniGoMani/user_data/mgm-config.json`   
([VSCodium](https://vscodium.com/) is open source and comes pre-installed with good color codes to make it easier to read `.json` or `.log` files, and many more too)   
    1. Follow [these 4 easy steps](https://www.siteguarding.com/en/how-to-get-telegram-bot-api-token) to create your own Telegram bot and fetch it's api-token, fill `token` under `telegram` up in `mgm-config-private.json` with this. Make sure to start a conversation with your bot before continuing!   
    1. Say `/start` to `@userinfobot` on Telegram to get your Chat ID, fill `chat_id` under `telegram` up in `mgm-config-private.json` with this.   
    1. Generate a strong key/password for `jwt_secret_key` under `api_server` in `mgm-config-private.json`   
    1. Choose and fill in a `username` and strong `password` also under `api_server` in `mgm-config-private.json`   
1. Open a terminal window and navigate to where you put `MoniGoMani` and type one of the following:   
    - `docker-compose pull` to pull in any updates to the Image if there are any
    - `docker-compose up --build` to build and start the bot & view its log or   
    - `docker-compose up -d`  to build and start the bot in the background.   
    - `docker-compose stop` to stop the bot.   
1. When running the included compose file FreqUI is already included and can be accessed from localhost:8080, 
   login is possible using the `username` and `password` from step 3.D.

That's it! You successfully set up Freqtrade through Docker, connected to Telegram, with FreqUI!   
You can now start using `MoniGoManiHyperStrategy` for HyperOpting/BackTesting/Dry/Live-running! Congratulations! :tada:   
But this is only the beginning, now please read the [MGM_DOCUMENTATION](monigomani.md) to learn how to use it properly!   
