# Mari0pository

The Mari0pository is a repository of community-made content for the game [Mari0](https://github.com/Stabyourself/mari0)
and its derivatives like [Alesan's Entities](https://github.com/alesan99/mari0_ae).

## Contributing

To add to the repository, you must create a pull request which modifies [data.json](data.json) to include your content.

Alternatively, you can [create an issue](https://github.com/qixils/mari0pository/issues/new/choose) describing your
asset and someone else may add it for you.

## Asset Schema

The following properties are available for all assets.

| Property           | Description                                                                                     |      Required?      |
|--------------------|-------------------------------------------------------------------------------------------------|:-------------------:|
| `type`             | The type of the asset. Must be `mappack`, `tileset`, `music`, `sound`, `character`, or `enemy`. |          ✅          |
| `name`             | The short name of the asset. Must be \[1,17] characters long.                                   |          ✅          |
| `long_name`        | The long name of the asset.                                                                     |          ❌          |
| `description`      | A short description of the asset. Must be at most three lines with 17 characters per line.      |          ❌          |
| `long_description` | A long description of the asset.                                                                |          ❌          |
| `version`          | The version of the asset in semantic versioning format.                                         |          ✅          |
| `author`           | The author of the asset. Must be \[1,14] characters long.                                       |          ✅          |
| `license`          | The license of the asset. Should be an [SPDX identifier](https://spdx.org/licenses/).           |          ❌          |
| `download`         | The data for this asset's download. See [Download Schema](#download-schema).                    | If homepage is null |
| `released`         | The date the asset was released. YYYY-MM-DD format.                                             |          ✅          |
| `updated`          | The date the asset was last updated. YYYY-MM-DD format. Defaults to the release date.           |          ✅          |
| `icon`             | The direct download link to the asset's icon.                                                   |          ❌          |
| `homepage`         | The link to the homepage of the asset.                                                          | If download is null |

### Game-Specific Asset Schema

The following additional properties are available for assets that are created for a specific version of the game.
This currently includes mappacks, tilesets, characters, and enemies.

| Property       | Description                                                                                     | Required? |
|----------------|-------------------------------------------------------------------------------------------------|:---------:|
| `game_version` | The version of the game this asset is tied to. See [Game Version Schema](#game-version-schema). |     ✅     |

## Download Schema

| Property   | Description                            | Required? |
|------------|----------------------------------------|:---------:|
| `url`      | The direct download link to the asset. |     ✅     |
| `filename` | The filename of the asset.             |     ✅     |

## Game Version Schema

| Property     | Description                                                                                                                                                                                          | Required? |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------:|
| `derivative` | A list of which derivative(s) of the game this asset was created for. Items must be `1.6`, `SE`, `AE`, or `CE`.                                                                                      |     ✅     |
| `ranges`     | A list of version ranges this asset is compatible with. The components of a version range separated by a space are AND'd, while the components separated into different items in the array are OR'd. |     ❌     |
