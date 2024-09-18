# SW2.5 Foundry Stat Block Importer for CSM
> Imports monster stat blocks from sw25.nerdsunited.com to Foundry VTT using PDF Pager and Bar Brawl

## Required Foundry VTT Modules
Please enable these modules on your world before importing the stat blocks generated by this script.
* [PDF Pager](https://github.com/farling42/fvtt-pdf-pager)
* [Bar Brawl](https://gitlab.com/woodentavern/foundryvtt-bar-brawl)

## How to Set-Up
Navigate to the directory of the Stat Block Importer using Git:
```
cd "YOUR DIRECTORY HERE"
```

Run the following commands with [npm](https://www.npmjs.com/):

```sh
$ npm install fs
```

```sh
$ npm install readline
```

```sh
$ npm install node-fetch@2
```

```sh
$ npm install he
```

Create a folder in your world called "pdfs", then add the `SWMonsters.pdf` file supplied in this repository to it.
Open `monster_stat_block.json` and navigate to the following section of the JSON:
```json
    "pdf-pager": {
      "customPDF": "worlds/YOUR-WORLD-HERE/pdfs/SWMonsters.pdf",
```
Replace "YOUR-WORLD-HERE" with the name of your world's folder.

Run the script using [Node.js](https://nodejs.org/en/download)

```sh
$ node convertStatBlocks.js
```

When prompted, enter a link to a specific stat block on sw25.nerdsunited.com or type the name of any monster. If performing the latter, the script will use the `?list` function of the API to search for a specific monster stat block.

Navigate to the Output folder and import that JSON file onto an empty newly-generated Actor. Congratulations! Your stat block should be properly imported, and the prototype token should have bars representing the monster's HP and MP.
