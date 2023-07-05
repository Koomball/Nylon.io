# .nyl Functions
## $if(condition){output};
returns the given output if the condition is met. <br>
Example 1:
```
$if(a S= "beans"){
$output.console{"this user is beans"};
};
```
Example 2 (using or)
```
$if(or[(a S= "beans"), (a S= "lemon)]){
$output.console{"this user is either beans or lemons"};
};
```
## $else{output}
connect to a `$if` block and this will output if the condition is not met. <br>
Example:
```
$if(a S= "beans"){
$output.console{"this user is beans"}
} $else{
$output.console{"this user is not beans"}
};
```
## $else.if(condition){output}
connect to a `$if` block and the code will work top to bottom until a condition is met if none are met it will run `$else` if one is given or just end the `$if` block. In this example we will use a function explained in the next part called `$var(name[value]);` and `$val{name};` <br>
Example:
```
$if(a S= "beans"){
$var(outcome["you are beans]);
} $else.if(a S= "lemon"){
$var(outcome["you are lemons"]);
} $else {
$var(outcome["you are nothing"]);
};

$output.console{$val{outcome}};
```
## $var(name[value])
this function will store a temporary value in the code that will go away once its done running, you input the name of the variable which is what you will use in `$val{name}` to output the `[value]` which will be whatever you want the value to be. <br>
Example:
```
$var(a['100']);
$output.console{$val{a}};
```
this would output `100` in the console.
