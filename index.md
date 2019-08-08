# DataCamp Widget Demo

<br>

Try the DataCamp Light interactive R console [HERE](datacamp-light-demo.html).

Or you can copy the [RMD file](https://github.com/DS4PS/datacamp-light-demo-for-rmd/raw/master/datacamp-light-demo.rmd) to try it out yourself.

<br>

## Tutorials in Action

Try out a [Mortgage Calculator](calc-mortgage.html)  [ [RMD](https://raw.githubusercontent.com/DS4PS/datacamp-light-demo-for-rmd/master/calc-mortgage.rmd) ]

<br>

We have customized some elements using CSS.

```
div.powered-by-datacamp{
   margin-bottom:40px;
   display: none;
}

div.datacamp-exercise{
   margin-bottom:40px;
}
.datacamp-exercise .dcl-btn-primary {
    background-color: LightSteelBlue; 
    color: white; 
}
```

And added question cues that are highlighted by placing them inside a questions div:

```
<div class="question">

* What arguments do you need?
* How many decimals do you need (consider the `round()` function.
* Don't forget a return statement!

</div>
```

CSS:

```
div.question{
  background-color: LightSteelBlue;
  border-radius: 10px;
  border: 1px solid lightgray;
  padding-top:10px;
  padding-bottom:10px;
  font-size: 85%;
  font-family: Verdana;
  /* font-weight: bold; */
  color: white;
  padding-left:05%;
  margin-bottom:40px;
}
```
