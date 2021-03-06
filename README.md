# Chainlol — Navigate Crypto

Inspired by Facebook's [bunnylol](https://www.quora.com/What-is-Facebooks-bunnylol) project, chainlol makes it faster to navigate to common crypto sites — instead of going to CoinGeiko.com and searching for olympus, you can just type in `p ohm` and the tool will automatically redirect you.

The tool is built with JS and **runs purely locally in the browser** so there are no securty implications about sending search results to an unknown server. 


## Example Commands

Command | Example | Description
--- | --- | ---
p, price | p olympus | Opens CoinGeiko dashboard for the spelled out coin.
tx | tx 0x000.. or tx 1123123 for SOL | Opens Etherscan or Solscan depending on the hash type.
w, wallet | w vitalik.eth | Opens the walllet based on the hash or the ENS name.
commands | commands | Lists available commands.
nft | nft chain runners | Searches for the NFT keyword in the OpeanSea.
s, swap | swap ohm dai | Opens uniswap with the two coins to swap.
ipfs | ipfs Qmd8nEQ2K6Uw67oFjM8FQo6K8qdvkaKMDwN91TBprC7EJ6 | Opens the file with the hash on IPFS.
ar | ar Qmd8nEQ2K6Uw67oFjM8FQo6K8qdvkaKMDwN91TBprC7EJ6 | Opens the file with the hash on ARWeave.
ipns | ipns kunalm.xyz | Opens the domain on IPNS.

## Setup

1. Open Chrome and click the three dots. Click `Settings` and scroll down to `Search Engines`.

2. Click `Manage Search Engines`.

3. Add a new search engine with the URL `https://chainlol.wonkalabs.xyz/#?q=%s`. Set both name and keyword to `chainlol`.

4. Make this the default search engine.

It should look like this:

<img width="608" alt="Screen Shot 2022-03-08 at 9 53 38 AM" src="https://user-images.githubusercontent.com/791388/157298422-564b4a60-c6dd-4c5b-ba59-4647fc6efa5a.png">


## Running Locally

Call `python3 -m http.server` from the main directory, then naviagte to `http://localhost:8000/?q=commands` 

## Deploying

Currently, chainlol is hosted on [fleek](https://fleek.co/).

Alternatively, you can host it on ipfs through Pinata:
```
ipfs-deploy . -p pinata -d cloudflare -t "your-domain.xyz $(date +"%m-%d-%Y %T")"
```

(this requires npm `ipfs-deploy` and setting a few .env variables. See [here](https://kunalm.xyz/posts/ipfs-website.html) for more details)
