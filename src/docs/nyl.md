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

### $var(name:{value}, {value});
stores a list of temporary values that is deleted once the code is done running, input a name you want to call the variable in the `name:` part and then put values in `{value}` seperated with a `,` for each value. (starts at `1`)
<details>
  <summary>Example</summary>

```
$var(a{"apple"}, {"orange"}, {"pear"});
$output.console{$val{a(2)}};

// output: orange
```
</details>

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

### $val{name(listNum)};
outputs a value from a list variable input what number value from the list you want to grab in the `(listNum)` section, or input `(-;SEPARATOR)` to output all the values with a given separator.
<details>
  <summary>Example</summary>

```
$var(a{"apple"}, {"orange"}, {"pear"});
$output.console{$val{a(2)}};
$output.console{$val{a(1)}};

// output 1: orange
// output 2: apple
```
</details>

<details>
  <summary>Example with (-;SEPARATOR)</summary>

```
$var(a{"apple"}, {"orange"}, {"pear"});
$output.console{$val{a(-;, )}};

// output: apple, orange, pear
```
</details>
## $constructor
a unique function in nylon this requires an extension from the list below to properly function, constructors are lists that can take in values and then be used to send information in bulk to api's and stored in detabases.

<details>
<summary> $constructor Extensions </summary>

## $constructor.build(name:{code});
used to build a constructor that can be used in `$constructor.new`

<details>
  <summary>Example</summary>

```
$constructor.build(profile{
    string(name)
    number(age)
    string(from)
};
```
</details> <br>

## $constructor.new(name:{constructor});
used to create a list with a constructor which will be ran in your `constructorHandler.nyl`
<details>
  <summary>Example</summary>

```
$thread(`src/functions/constructorHandler.nyl`:{profile});
$constructor.new(myProfile{profile})
    myProfle.set.name{john};
    myProfile.set.age{69};
    myProfile.set.from{australia};
```
</details> <br>

</details> <br>

## $output
requires an extension to work, whatever is inputted is outputted into the directed extension.
<details>
<summary> $output Extensions </summary>

## $output.console{output};
text here
<details>
<summary> Example </summary>

```
$output.console{"abc"}

// outputs abc into the console when the code is ran.
```
</details> <br>

</details> <br>

## $else
only works inside the second argument of `[;]` blocks with a `if()` or `elseif()` declaration, if the condition given is met then the `[;]` block will only read before `$else` if the condition is not met it will only read after `$else`
<details>
<summary> Example </summary>

```
$var(a{$randNum{0, 10}});

[if(a <= 5);
    $console.output{"abc"};
$else
    $console.output{"cba"};
];

// if variable a is 5 or lower the console will output abc.
// if the variable a is above 5 the console will output cba.
```
</details> <br>

## $elseif(condition)
only works inside of a `[;]` block with a `if()` or `elseif()` declaration, if the condition prior to this one is not met then it will check this condition, if the condition is met it will run the outcome below and end the block, if the condition is not met it will move on or if theres nothing to proceed to it will end the block.
<details>
<summary> Example </summary>

```
$var(a{$randNum{0, 10}});

[if(a <= 3);
  $output.console{"house"};
  // if a is 3 or lower console will output house.
$elseif(a <= 6);
  $output.console{"car"};
  // if a wasnt 3 or lower but is 6 or lower then the console will output car.
$else
  $consle.output{"tree"};
  // if a wasnt 3 or lower and wasnt 6 or lower this $else will run and the console will output tree.
];
```
</details> <br>

# .nyl block declarations.
always goes in the first argument of `[;]` blocks.

## [;]
this is a block it changes the way the code is handled either to allow it to repeat, or only run if a condition is met or to only make it run when something happens. the block is split it two parts `declaration` and `outcome` which is built like this.
```
[declaration;
  outcome
];
```
below is a list of declarations that can be used inside of `[;]`

## if(condition)
can only be placed in the first argument of a `[;]` block.
<details>
<summary> Example </summary>

```
$var(a{$randNum{0, 10}});

[if(a <= 5);
    $output.console{"abc"}
];

// if the variable a ends up being below or equal to 5 then the code will output abc into the console.
```
</details> <br>

## on.
requires an extension to work, makes the block only run if the given extension occurs while the code is being run.
<details>
<summary> on Extensions </summary>

## on.ping(name);
runs when a `$ping` function with the same name as the one given is ran.
<details>
<summary> Example </summary>

Simple Example
```
$var(a{$randNum{0, 10}});

[if(a < 5);
  $ping(test)
];

[on.ping(test);
  $output.console{"abc"}
];

// if a is below 5 then it will run $ping(test) which will trigger [on.ping(test);outcome]
```

Advanced example.
```
$var(a{$randNum{0, 10}});

[if(a < 5);
  $ping(ask input)
  $waitFor.ping(input given)
  
  $output.console{$val{input}};
];

[on.ping(ask input);
  $output.console{"input some text"}
  [on.input.console;
    $var(input{$input.console});
    $ping(input given)
  ];
];

// this though a horrible way to do it, will ask the user to input some text if the variable a is below 5, it will then output whatever text was given back out into the console.
```
</details> <br>
</details> <br>

# advanced functions & block declarations.
## isolate
can only be a declaration in a `[;]` block will isolate the code inside meaning once its done any stores `$var`'s or other temporarily stored data is deleted once the block ends. this can be used to delete data you no longer need before the code ends.
<details>
  <summary>Example</summary>

```
$var(a{'5'});

[isolate;
  $var(a);
];

$output.console{$val{a}};

// output: ERROR: temporary variable "a" doesnt exist. Either create it with $var(a{value})
or if this is meant to happen use $error.await($val{output}) at the top of your code.
```
</details>

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
