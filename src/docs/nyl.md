# Nylon Documentation
text here one day
# .nyl Functions
always starts with `$` <br>
## $var(name:{value});
stores a temporary variable in the code that is deleted once its done running, input a name you want to use to call the variable in the `name:` part and then put a value to output whenever the variable is called in the `{value}` part.
<details>
  <summary>Example</summary>
    
```
$var(a{'5'});
$output.console{$val{a}};

// output: 5
```
</details> <br>

## $val{name};
outputs the value of the given variable in `{name}`
<details>
  <summary>Example</summary>

```
$var(a{"test"});
$output.console($val{a}}

// output: test
```  
</details> <br>

## $constructor
a unique function in nylon this requires an extension from the list below to properly function, constructors are lists that can take in values and then be used to send information in bulk to api's and stored in detabases.
### $constructor.build(name:{code});
used to build a constructor that can be used in `$constructor.new`
<details>
  <summary>Example</summary>

```
$constructor.build(profile{
    string(name:{john})
    number(age:{69})
    string(from:{australia})
};
```
</details> <br>

# Examples
Example (using $var and $if blocks)
```
$var(random:$randNum{0, 10});

[if($val{random} <= 5);
    $var(response:"beans");
$else
    $var(response:"lemons");
];

$output.console{$val{random}};
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
  $var(random:{$randNum{0, 10}});
  $constructor.new[testEmbed:{embedBuilder}];
    [if($val{random} <= 5);
      testEmbed.setTitle{"beans"};
      testEmbed.setDescription{"you are beans"};
    $else
      testEmbed.setTitle{"lemons"};
      testEmbed.setDescription{"you are lemons"};
    ];
$output.interaction.reply{embed: [testEmbed]}; 
];
