# Nylon Documentation
Example (using $var and $if blocks)
```
$var(random{$randNum{0, 10}});

[if($val[random] <= 5);
    $var[response:"beans"];
$else
    $var[response:"lemons"];
];

$output.console{$val[response]};
```

Example (discord.nyl embed command)
```
$thread[discord.nyl:{slashCommandBuilder, embedBuilder, interactionHandler}];
$thread[src/functions/slashCommandHandler.nyl:{slashCommandHandler}];

$constructor.new(slash:{slashCommandBuilder});
    slash.setTitle{"test"}
    slash.setDescription{"test command"} >;
[error.catch(uploadError); 
    $slashCommandHandler[$constructor.find(slash)]
    [if(uploadError S= false);
        $output.console{"test failed to upload"}
        $terminate
    ];
];

[on.Interaction.Command(test);
  $var(random{$rand.Num{0, 10}});
  $constructor.new[embedBuilder(testEmbed)];
    [if($val[random] <= 5);
      testEmbed.setTitle{"beans"};
      testEmbed.setDescription{"you are beans"};
    $else
      testEmbed.setTitle{"lemons"};
      testEmbed.setDescription{"you are lemons"};
    ];
$output.interaction.reply{embed: [testEmbed]}; 
];
