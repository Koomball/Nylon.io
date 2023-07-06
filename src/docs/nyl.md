# Nylon Documentation
Example (using $var and $if blocks)
```
$var[random{$randNum{0, 10}}];

[if($val[random] <= 5);
    $var[response:"beans"];
$else
    $var[response:"lemons"];
];

$output.console{$val[response]};
```

Example (discord.nyl embed command)
```
$thread[discord.nyl{slashCommandBuilder, embedBuilder, interactionHandler}];
$thread[src/functions/slashCommandHandler.nyl{slashCommandHandler}];

$constructor.new[slash:{slashCommandBuilder}];
    < slash.setTitle{"test"}
      slash.setDescription{"test command"} >;
[(error).catch(uploadError); 
$slashCommandHandler[slash.construction]
[(if(uploadError S= gail
