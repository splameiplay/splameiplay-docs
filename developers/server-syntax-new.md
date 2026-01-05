# Server Syntax (New)

{% hint style="info" %}
You may not be able to provide the legacy and new data structure for full compatibility between SplameiPlay Bloom depending on how your provide this data to SplameiPlay. The only known conflict is displaying notices and play-data. Other information should not conflict
{% endhint %}

SplameiPlay needs data to access data through a Http `GET` request. Below is the data SplameiPlay expects. The URL your provided in the custom project file will be shown in the table as the '\~' symbol

## Root Data (Version)

SplameiPlay requires the version code file to be in the root of the URL. This code needs to be incremented every time you want SplameiPlay to update your project. It's recommended to do this every update and start on number 1000 however, you can choose your own system however, the value returned must be a integer. The file must be located at `~/ver` when requested.

## Notices and play-data

Notices are located in their own folder. Each language has it's own code used for play-data and notices. Play-data's files must be located at `~/play-data/<language-code>` and notices must be located at `~/notices/<language-code>`. You must replace `<language-code>` with each of the following for each language. You have to return a value to English though you do not have to for the other languages since SplameiPlay will fallback to English if it returned an error.

| Language           | Language Code |
| ------------------ | ------------- |
| English (required) | en            |
| Japanese           | jp            |

### Play data syntax

When requesting play-data, SplameiPlay requires a certain syntax to be returned. Below is a table of the expected data:

| Name          | Description                                                                                                                                                                                                 | Example                                                                                                                                                |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| About         | A short description of the project                                                                                                                                                                          | Nimokion is a new puzzle, platformer game from Splamei. Explore the story and world of the game and discover what whet wrong, and fix all the mistakes |
| Specs         | The specifications for your projects. SplameiPlay only displays this, not enforce.                                                                                                                          | <p>Windows 10+</p><p>DirectX 11<br>.NET Standard 2.1</p>                                                                                              |
| Ratings       | The age rating of your project                                                                                                                                                                              | Age: 7+                                                                                                                                                |
| Developers    | The developers and publishers of the project                                                                                                                                                                | Developer: Splamei                                                                                                                                     |
| Languages     | The languages your project supports                                                                                                                                                                         | English, Japanese                                                                                                                                      |
| Terms         | A basic description or name of the terms of your project                                                                                                                                                    | Splamei Project TOS                                                                                                                                    |
| Input Methods | <p>The ways players can use your project (must contain only Keyboard, Mouse or/and Controller separated by commas and no spaces)<br><br>SplameiPlay currently will discard this value as it is not used</p> | Keyboard,Mouse,Controller                                                                                                                              |

## Releases

### Windows

In order for SplameiPlay to work for Windows, SplameiPlay must be able to request two separate pieces of data. Firstly, `~/releases/windows/downloadable` which must return one of the following:

| Data         | Meaning                                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Downloadable | The project can be downloaded                                                                                           |
| Unreleased   | The project is unreleased (you should not allow access to `~/releases/windows/release.zip`)                             |
| Unavailable  | The project is released but should not be downloaded  (you should not allow access to `~/releases/windows/release.zip`) |

You must also contain a zip file in `~/releases/windows/release.zip` for SplameiPlay to download the project correctly. You do not have to provide this if SplameiPlay should not be able to download the project. The file to be executed must be provided in the root of the extracted zip files contents to be launched correctly.
