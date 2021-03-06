# DataCamp Light Demo for RMD Files

The [DataCamp Light](https://github.com/datacamp/datacamp-light) javascript library allows you to add R widgets to your HTML files so that students can do interactive examples using code. The `tutorial` package allows you to easily add these widgets to RMD documents:

[Try it out](http://ds4ps.org/datacamp-light-demo-for-rmd/.)



# The `tutorial` Package

DataCamp has created an R package called [`tutorial`](https://github.com/datacamp/tutorial) to integrate the DataCamp Light widget into R Markdown documents.

```r
devtools::install_github( "datacamp/tutorial" ) 
```

# Example RMD

This example of a simple tutorial comes from the `tutorial` [vignette](https://github.com/datacamp/tutorial).


````markdown
---
title: "Example Document"
author: "Your name here"
output:
  html_document:
    self_contained: false
---

```{r, include=FALSE}
tutorial::go_interactive()
```

```{r ex="create_a", type="pre-exercise-code"}
b <- 5
```

```{r ex="create_a", type="sample-code"}
# Create a variable a, equal to 5


# Print out a

```

```{r ex="create_a", type="solution"}
# Create a variable a, equal to 5
a <- 5

# Print out a
a
```

```{r ex="create_a", type="sct"}
test_object("a")
test_output_contains("a", incorrect_msg = "Make sure to print out `a`.")
success_msg("Great!")
```

````

# Options

## self_contained: false

Allows the most recent version of DataCamp light to be fetched each time the webpage opens. 

## go_interactive()

Turns R chunks into interactive widgets.

```
go_interactive( greedy = TRUE, height = 300 )
```

With the greedy argument, you can control which elements of your R Markdown document are
converted into DataCamp Light chunks. By default greedy is TRUE, leading to all R code chunks to
be converted to interactive frames. Only chunks for which you specify the option `tut = FALSE` are
not converted. If ‘greedy‘ is FALSE, only chunks for which you specify `tut = TRUE` are converted.


## type="pre-exercise-code"

R chunk option for specifying the type of chunk in the tutorial window. 

* **type="pre-exercise-code"** allows you to load packages or data silently  
* **type="sample-code"** provides starter code for the R script
* **type="solution"** displays after the user runs their own code  
* **type="sct"** performs a [submission correctness test](https://instructor-support.datacamp.com/en/articles/2312002-submission-correctness-tests) based upon user code


# Code Validation 

Test your code before launching tutorials using testwhat.

https://datacamp.github.io/testwhat/
