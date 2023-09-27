# Nylon scrapbook

- Nylon (nyl) File Layout & NylonList (nys)
  - Folders
📁 > project <br>
    📁 > nylon (folder / dont modify)<br>
    📁 > src (folder)<br>
      💾 > startScript.nyl <br>
    📁 > watchers (folder) <br>
      💾 > exampleWatcher.nyl <br>
    📁 > variables (folder) <br>
      💾 > exampleFrame.nyl <br>
    📁 > project (folder) <br>
  💾 > config.nys <br>
  💾 > packages.nys <br>

  - Nylon List
Nylon Lists / under the file extension .nys is used for configuration files within nylon primarily `config.nys` and `packages.nys`. <br>
***Config.nys Example***
```
- This is an example of the config.nys file that would automatically be created when you install nylon into a folder.

- Nylon Settings / Configuration !
  - Watcher Settings
    > Constant Watchers Max: 9;
      > Constant Watchers Folder: src/watchers;
    > Dormant Watchers Max: 30;
    > Active Watchers Max: 5;

- Console Settings
  > Output: Yes;
  > Output Errors: Yes;
    > Offer Error Resolve: Yes;
    > Output Layout Errors: No;

  > Advanced Error Outputs: No;
    > Offer Possible Missing Packages: No;
```
 <br>
***Packages.nys*** *(example with discord.nyl & environment.nyl installed)* 
```
- Installed Packages
    - discord.nyl
      > enabled: yes;
    - environment.nyl
      > enabled: yes;

- discord.nyl
  - Developed By: Nylon Development.
  - Version: v0.1
    > Core File: src/core.nyl;
    > Command Listener: src/watchers/commandHandler.nyl;
    > Environment (put Env if using environment.nyl): Env;

- environment.nyl
  - Developed By: Nylon Development.
  - Version: v0.1
    > Use enviroment.nyl?: Yes;
```
- Console Commands
  - Settings
    - Settings List
`nyl s`, `nyl settings` <br>
Displays list of all settings and there configurations. <br>
```
OUTPUT:
nylon settings / configuration.
  Constant Watchers Max: 9
  Dormant Watchers Max: 30
  Active Watchers Max: 5

  Output: Yes
  Output Errors: Yes
  Offer Error Resolve: Yes
  Advanced Error Outputs: No
    - Output Layout Errors: No
    - Offer Possible Missing Packages: No

```
 <br>
    - Settings Set
`nyl sset <settingKeyword> <configuration>`, `nyl settings set <setting> <configuration>` <br>
Setting Keywords:<br>
Constant Watchers Max = `ConstantWatchers` <br>
Dormant Watchers Max = `DormantWatchers` <br>
Active Watchers Max = `ActiveWatchers` <br>
Output = `Output` <br>
Output Errors = `OutputErrors` <br>
Offer Error Resolve = `ErrorResolve` <br>
Advanced Error Outputs = `AdvancedErrors` <br>
Output Layout Errors = `LayoutErrors` <br>
Offer Possible Missing Packages = `MissingPackage` <br>

Setting Configurations:<br>
Constant Watchers Max = `Must be 0 or above (or - for infinite)` <br>
Dormant Watchers Max = `Must be 0 or above (or - for infinite)` <br>
Active Watchers Max = `Must be 0 or above (or - for infinite)` <br>
Output = `Yes / No` <br>
Output Errors = `Yes / No` <br>
Offer Error Resolve = `Yes / No` <br>
Advanced Error Outputs = `Yes / No` <br>
Output Layout Errors = `Yes / No` <br>
Offer Possible Missing Packages = `Yes / No` <br>

 <br>
    - Constant Watchers Max
text
    - Dormant Watchers Max
text
    - Active Watchers Max
text
    - Advanced Error Outputs
- Nylon
**Index**
> File Types
  > Watchers
  > Nylon List (nys)

- File Types
text
  - Watchers
text
    - Constant Watchers
Constant watchers are stored in `project/src/watchers` and constantly run and await triggers while scriptStart.nyl is running. <br>
**Example:** <br>
*File Name: exampleWatcher.nyl* | *Location: ../src/watchers* 
```
thread[nylon(watcher)];
  
  listen: ../src/project/
    for: [
      - Green
      - Red
      - Yellow
    ];

  store: Cool Person,
    value: false;

  when: Green,
    then: output[console]: "Green";

  when: Red,
    then: wait: 5s, then: 
    output[console]: "Red";

  when: Yellow
    if Cool Person is false,
      then: output[console]: "Yellow, also your not cool";
      else: output[console]; "Yellow, also your cool";
```
 <br>
*File Name: exampleTrigger.nyl* | *Location: ../src/projects*
```

```
- Discord.nyl