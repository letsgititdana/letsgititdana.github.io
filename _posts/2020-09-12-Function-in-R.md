---
title: "FUNCTION IN R"
date: 2020-09-12 10:45:00 -0400
categories: R
---


# Function in R

R has a large number of in-built functions and the user can create their own functions.



## Defining and Calling a Function

```R
function_name <- function(arg_1, arg_2, ...) {
   Function body 
}
```



### Example 1: Defining a function to print squares of numbers in sequence

```R
function1 <- function(a) {
  for(i in 1:a) {
    b <- i^2
    print(b)
  }
}

function1(3)			# calling the function returns 1 4 9
```



### Example 2: Calling a function with default arguments

```R
function2 <- function(p="R"){
  print(p)
}

function2 <- function(p="R"){
  print(p)
}

function2()						# returns "R"
function2(p="PYTHON")	# returns "PYTHON"
function2("JAVA")			# returns "JAVA"
```



### Example 3: Calling a function by position and by name

```R
function3 <- function(a,b,c) {
   result <- a * b + c
   print(result)
}

# Call the function by position of arguments.
function3(5,3,11)			# returns 26

# Call the function by names of the arguments.
function3(a = 11, b = 5, c = 3)			# returns 58
```



### Example 4: Defining and calling a function with variable number of arguments

```R
function4 <- function(...) {
  data <- list(...)
  sum <- 0;
  for(item in data) {
    if(is.numeric(item))
      sum <- sum + item
    else
      print(item)
  }
  return(sum)
}

function4(10,20,30)							# returns 60
function4(10,20,"test", 30,40)	# returns "test" 100

```



