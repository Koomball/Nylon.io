![image](https://github.com/Koomball/Nylon.io/blob/2f10c5391a90a5df8e07580a9e5217f62e3b0466/4634634643.png)

<i>Nylon is a in development programming language that takes inspiration from bdscript2 and yaml. Nylon is not for discord bots and is being developed for game development but will have the tools to make any package you desire including the future discord.nyl planned much later after the languages release. Nylon can be intergrated with nearly any language to form as a universal translator that can be highly customised for whatever purpose you need it for.</i>

> <b>Here from BDFD?</b>
> Below is a condensed list of some of the major differences between BDFD and The Nylon Design Engine if your planning to use it for Discord bot development. <br>
> <details> <summary> Open List </summary> 
> 
> ***Different syntax*** <br>
> nylon only uses $ for most functions but blocks dont use any start below is an example of this. <br>
> ```
> $tempVar[num;$randomNum[1;10]]
>
> if $get[num] > 5 then:
>  - $consoleOut[above 5]
> else:
>  - $consoleOut[5 or lower]
> endif
> ```
>
> ***Multiple Split Texts.*** <br>
> nylon expands the common textSplit feature found in many languages by allowing you to store multiple textSplits and edit them simultaneously instead of having save and switch between them constantly. <br>
>
> ***No Free Hosting.*** <br>
> you must source your own hosting to power the Nylon Design Engine or host on your own device.
> 
> ***No Free Data Storage.*** <br>
> you must store data locally or source your own data servers.
</details>

# Nylon Design Engine
The Nylon Design Engine is the code engine needed to use Nylon and NILD. Nylon views similar to Visual Studio Code but has a variables section. When creating projects you need to select a language to thread this will be the language that the Nylon language will operate on and allows you to use the nylon language to develop stuff for already existing projects that use other languages. (for example modding a game that uses java or lua) <br>
You can also thread with Nylon Direct which is a solely nylon system meaning it cannot communicate with other languages unless you thread them within the file. <br>

# Nylon Programming Language
The Nylon Programming Language takes inspiration from Bot Designer For Discords bdscript2 and the storage language yaml turning coding into a easily readable and translatable step by step process. <br>

# NILD (Nylon Intergration Language for Data)
Data is called in through nylon with `$getData[source;key;(key2;...)]` below is two examples of this. <br>
nild file (inventorys.nild):
```
- user1
  [ > Dirt: 0;
    > Stone: 0;
  ]
- user2
  [ > Dirt: 3;
    > Stone: 5;
  ]
```
nylon code:
```diff
$getData[src/inventorys.nild;user1;Dirt]

+ Output: 0
```

<details> 
**config.nyls**
<details> <summary> config.nyls </summary>
  
```
- nylon config.nyls

- Settings
  [ - Watchers
      > Max Constant Watchers: 9;
      > Max Dormant Watchers: 30;
      > Max Active Watchers: 9;
    - Console / Output
      > Output: true;
      > Ouput Errors: true;
  ]

- File Configuration.
  [ > Watcher Folder: src/watchers/
    > Start Script: startScript.nyl
    > Packages Config: packages.nyls
  ]
```

---

</details> <summary>unsorted stuff</summary>

# Console Commands
**Install Package** <br>
Command: `nyl install` <br>
Example: `nyl i discord.nyl` <br>
use @ after package name to define specific version. <br>
Example: `nyl i discord.nyl@v0.1` <br>

**Run startScript.nyl** <br>
Command: `nyl startScript`

dnylconfig.nyls
```
- dnylconfig.nyls
  [ - Developed By: Nylon Developments
    - Version.
      [ > ver: 0.1; ]
    - Config.
      [ > enabled: true; ]
  ]
```
</details>


