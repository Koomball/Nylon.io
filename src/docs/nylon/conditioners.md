# Conditioners
`N=` Equal too for numbers. <br>
`S=` Equal too for strings. <br>
`>=` Above or equal too. <br>
`<=` Below or equal too. <br>
`<` below. <br>
`>` above. <br>
`?=` equals undefined/null. <br>

# Advanced Conditioners.
`or[(condition 1), (etc), (etc)]` - Returns true if any one of the conditions meet true. <br>
Example. <br>
```
$if(or[(data.a N= 5), (data.a N= 2)]){
  output.console("beans");
};
```
`and[(condition 1, (etc), (etc)]` - Returns true if all conditions are met. <br>
Example. <br>
```
$if(and[(data.a > 5), (data.b > 2)]){
  output.console("beans");
};
```
