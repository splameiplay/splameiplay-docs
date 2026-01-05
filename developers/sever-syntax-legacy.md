# Sever Syntax (Legacy)

{% hint style="warning" %}
As of SplameiPlay 4.2 Bloom, this server syntax is no longer in use and is deprecated. Please use the updated syntax for modern SplameiPlay support
{% endhint %}

SplameiPlay needs data to access data through a Http `GET` request. Below is a table with all the data SplameiPlay expects. The URL your provided will be shown in the table as the '\~' symbol

| URL                  | Expected Syntax | Use                                                                                                                                              |
| -------------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| \~/build-windows.zip | .zip file       | The zip file containing the files of the project                                                                                                 |
| \~/downloadable.txt  | Int (0, 1 or 2) | The file containing if the project can be downloadable. 0 for allowing a download, 1 for an unavailable project and 2 for an unreleased project. |
| \~/notice            | String          | The file containing the notice showing on the project page                                                                                       |
| \~/play-data         | String          | The data used by SplameiPlay's about section. More infomation below                                                                              |
| \~/ver               | Int             | The version code of the project. Increment it every update you want to enforce                                                                   |

The 'play-data' file uses a special syntax as seen below. The data must be in the order as shown.

| Name       | Description                                                                             | Example                                |
| ---------- | --------------------------------------------------------------------------------------- | -------------------------------------- |
| About      | A short description of the project                                                      | This is the description of my project! |
| Specs      | The specifications for your projects. SplameiPlay only displays them, not enforce them. | DirectX 11, Windows 10+                |
| Ratings    | The age rating and reviewer ratings of your project                                     | Age: 7+                                |
| Developers | The developers and publisher of the project                                             | Developer: Splamei                     |
| Languages  | The languages your project supports                                                     | English, Japanese                      |
| Terms      | A basic description or name of the terms of the project                                 | Splamei Project TOS                    |
