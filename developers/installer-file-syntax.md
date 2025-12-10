# Installer File Syntax

Below are all of the commands you can put in an installer file:

<table><thead><tr><th>Command</th><th>Expected Syntax(s)</th><th>Example</th><th>Meaning</th><th data-type="checkbox">Required</th></tr></thead><tbody><tr><td><code>FileVer</code></td><td>File Version (1.0)</td><td><code>FileVer=1.0</code></td><td>The version of the installer file (must be the first command)</td><td>true</td></tr><tr><td><code>Type</code></td><td>Installer Type</td><td><code>Type=1</code></td><td>The type of the installer file</td><td>true</td></tr><tr><td><code>Name</code></td><td>String</td><td><code>Name=SplameiPlay</code></td><td>The name of the project</td><td>true</td></tr><tr><td><code>Author</code></td><td>String</td><td><code>Author=Splamei</code></td><td>The author of the project</td><td>true</td></tr><tr><td><code>SupportsWindows</code></td><td>Boolean</td><td><code>SupportWindows=True</code></td><td>Whether or not the project supports Windows</td><td>true</td></tr><tr><td><code>ExeName</code></td><td>String</td><td><code>ExeName=SplameiPlay.exe</code></td><td>The file to be opened with an installer file</td><td>true</td></tr><tr><td><code>Url</code></td><td>String</td><td><code>Url=https://veemo.uk/net/splameiplay/</code></td><td>The base URL that SplameiPlay uses to get most of it's data (must end in a / and must support a <code>GET</code> http request)</td><td>true</td></tr><tr><td><code>NoticesUrl</code></td><td>String</td><td><code>NoticesUrl=https://vemeo.uk/splameiplay</code></td><td>The URL to open when 'All Notice' on the project page</td><td>true</td></tr><tr><td>P<code>rojectUrl</code></td><td>String</td><td><code>ProjectUrl=https://veemo.uk/splameiplay</code></td><td>The URL to open when 'More Info' is proess on the project page</td><td>true</td></tr><tr><td><code>TermsUrl</code></td><td>String</td><td><code>TermsUrl=https://veemo.uk/splamei-project-tos</code></td><td>The project to open when 'Full Terms' is pressed on the project page</td><td>true</td></tr></tbody></table>

Using this, your installer file will look something like this:

```
FileVer=1.0
Type=1

Name=Rhythm Plus
Author=Splamei

SupportsWindows=True

ExeName=Rhythm Plus - Splamei Client.exe
Url=https://www.veemo.uk/net/r-plus/pc/
NoticesUrl=https://www.veemo.uk/net/r-plus/pc/
ProjectUrl=https://www.veemo.uk/net/r-plus/pc/
TermsUrl=https://www.veemo.uk/net/r-plus/pc/
```
