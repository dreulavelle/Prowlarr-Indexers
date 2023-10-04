# Torrentio Integration with Prowlarr

This README will guide you through the process of adding Torrentio as a custom indexer to your Prowlarr installation using the `torrentio.yml` configuration file.

## Docker Install

1. **Checkout this repo via git clone**

   ```
   git clone https://github.com/dreulavelle/Prowlarr-Indexers.git 
   ```

2. **change directory to the newly git cloned directory**

   ```
   cd Prowlarr-Indexers
   ```

3. **Start Docker**

   ```
   docker compose up -d
   ```

**More Info**

   visit https://docs.linuxserver.io/images/docker-prowlarr for more info on the configuration of the base prowlarr container

## Direct OS Install

## Prerequisites

- Prowlarr must be installed and running on your system.

## Instructions

1. **Download the Configuration File**

   First, download the `torrentio.yml` configuration file from the following link:

   [torrentio.yml](https://github.com/dreulavelle/Prowlarr-Indexers/blob/main/Custom/torrentio.yml)

2. **Create a Custom Directory**

   Create a directory called `Custom` within the Prowlarr configuration directory under the `Definitions` directory. If it doesn't exist already, you can create it in the following location:

   ```
   <Prowlarr_Config_Directory>/Definitions/Custom/
   ```

3. **Place the Configuration File**

   Place the downloaded `torrentio.yml` file into the `Custom` directory you created in the previous step.

4. **Restart Prowlarr**

   Restart Prowlarr to apply the changes.

5. **Add Torrentio as a Custom Indexer**

   Once Prowlarr has restarted, you can add Torrentio as a custom indexer by following these steps:

   - Go to the Indexers page in Prowlarr.
   - Click the "+" button to add a new indexer.
   - Enter "Torrentio" and search, select Torrentio from the list.
   - Edit the default options if necessary.
   - Save your changes.

6. **Using Torrentio as a Search Source**

   Torrentio will now be available as a search source in Prowlarr. You can use it to search for torrents and add it to your Sonarr/Radarr clients.

   To search on Prowlarr (Prowlarr only):

   - Click on "Search."
   - Enter your query.
   - Select the appropriate search type (TV Search or Movie Search Only).
   - You can use IMDb ID for precise movie or TV show searches using the format `{imdbID:tt123456}`.
![image](https://github.com/dreulavelle/Prowlarr-Indexers/assets/5782630/1c437cf5-c6c5-4fe6-9963-61dd5590eefc)

   - Alternatively you can use Season/Episode as `{ImdbId:tt1234567}{Season:00}{Episode:00}`
![image](https://github.com/dreulavelle/Prowlarr-Indexers/assets/5782630/87a2f007-dd17-419f-b5d8-1063aca2daa7)


You have successfully integrated Torrentio with Prowlarr. Happy searching and downloading!

# Validating The Indexer with the Cardigann Schema (v9)

The indexer can be validated using the schema from Cardigann.

```js
ajv test -d ".\Custom\torrentio.yml" -s ".\v9-schema.json" --valid --all-errors -c ajv-formats --spec=draft2019
```

Note that the following npm packages are required `ajv-cli-servarr ajv-formats` These can be installed globally on your system with `npm install -g ajv-cli-servarr ajv-formats`
