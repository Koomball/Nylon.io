# discord.nyl Embeds
Example Embed:
```
// calling the discord.nyl resources from the source package.
$thread[$constructor.build]{
  [`discord.nyl`[slashCommandBuiler, embedBuilder, interactionHandler]]};
$thread[slashCommandHandler]{
  [`src/functions/slashCommandHandler.nyl`[slashCommandHandler]]};

// making a slash command
$constructor.new[slashCommandBuiler(slash)];
  slash.setName{"test"};
  slash.setDescription{"test command"};

// using our slashCommandHandler in our setup.nyl file we will add the slash command to the queue to be uploaded through slashCommandHandler.nyl
[$error.catch($slashCommandHandler[slash])
  
$output.console{"command test.nyl failed to upload"};
$terminate
];

// responding to the command
[($on).Interaction.Command(test)
  $var(random{$rand.Num{0, 10}});
  $constructor.new[embedBuilder(testEmbed)];

[($if($val[random] <= 5))
  testEmbed.setTitle{"beans"};
  testEmbed.setDescription{"you are beans"};
($else)
  testEmbed.setTitle{"lemons"};
  testEmbed.setDescription{"you are lemons"};
];
$output.interaction.reply{embedHandler: [testEmbed]}; 
];
```
