# .nyl Checklist Index
[Skip to checklist](#nyl-checklist) <br>
[Future Ideas Checklist](checklist/futureChecklist.md) <br>
- ***Development Status Icons:***
  - `🟢 = Finished & Live`, `🟣 = Live for Testing`, `🟡 = In Development`
  - `🔵 = Development Paused`, `🔴 = Unstarted`
  - `⚫ = Task Depricated / Wont be done`
- ***Task Type Icons:***
  - `⚙️ = .nyl Core`
    - `Related directly to the core .nyl / nylon language and how it works.`
  - `💾 = .nyl integration`
    - `Important intergrations for .nyl so it can be utalized better.`
  - `📦 = Package`
    - `Packages / Extensions for .nyl to allow the user to make cool stuff.`
  - `💽 = Package Integration`
    - `Important integrations and api's for discord.nyl to function.`
- ***Function Type Icons:***
  - `⚙️ = Block Function`
    - `Always starts with $ and has a {output} and normally a (condition).`
  - `📜 = Functions`
    - `Always starts with $ could have a (argument) and will output different things.`
  - `🧮 = Conditioners`
    - `Used to compare strings or numbers.`
  - `🔑 = Function extensions`
    - `Modifies the output of extensions is always added after a fullstop in a function.`
  


# `🟡` `⚙️` Nylon
> - `🔴` `⚙️` Block Functions.
>   - `🔴` `⚙️` $if(condition){output};
>   - `🔴` `⚙️` $else{output};
>   - `🔴` `⚙️` $else.if(condition){output};
> - `🔴` `🧮` Conditioners.
>   - `🔴` `🧮` N= (Equal too, for numbers)
>   - `🔴` `🧮` S= (Equal too, for strings)
>   - `🔴` `🧮` >= (Above or Equal)
>   - `🔴` `🧮` <= (Below or Equal)
>   - `🔴` `🧮` > (Above)
>   - `🔴` `🧮` < (Below)
>   - `🔴` `🧮` ?= (Equals Null/undefined/etc)
>   - `🔴` `🧮` X= (Doesnt equal, works for both strings and numbers.)
>   - `🔴` `🧮` or[(condition 1), (etc), (etc)]
>   - `🔴` `🧮` and[(condition1), (etc), (etc)]
> - `🔴` `📜` Functions.
>   - `🔴` `📜` $var(name{value});
>   - `🔴` `📜` $val(name);
>   - `🔴` `📜` $thread(name{value});
> - `🔴` `🔑` Function Extensions.
>   - `🔴` `🔑` .separateNumber(seperator); `Note; added a separator to the output if its a number: 14412532.separateNumber(,); = 14,412,532`
>   - `🔴` `🔑` .round(decimalPoint); `Note; rounds the number to the given decimal point: 41.41431.round(2); = 41.41`
>   - `🔴` `🔑` .collapseNumber; `Note: collapses the number into its notation: 63426342.collapseNumber; = 63.4M`

# - `🔴` `💾` Nylon mongoDB intergration ⟶ [Full Checklist Here]()
> - `🔴` `💾` Nylon SQL intergration ⟶ [Full Checklist Here]()
> - `🔴` `💾` Nylon Other Database Integration ⟶ [Full Checklist Here]()
> - `🔴` `📦` Discord.nyl v0.0.1 alpha ⟶ [Full Checklist Here]()
>   - `🔴` `💽` Discord api integration  ⟶ [Full Checklist Here]()
>   - `🔴` `💽` MongoDB integration  ⟶ [Full Checklist Here]()
>   - `🔴` `💽` SQL integration  ⟶ [Full Checklist Here]()
>   - `🔴` `💽` Other Database Integration  ⟶ [Full Checklist Here]()
