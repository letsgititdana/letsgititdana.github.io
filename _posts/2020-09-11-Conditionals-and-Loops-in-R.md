---
title: "CONDITIONALS AND LOOPS IN R"
date: 2020-09-11 10:50:00 -0400
categories: R
---

# Conditionals and Loops in R

How to use control structures like If-Else statements, for loops, while loops in R



## 1. Conditionals in R (if, ifelse, switch)

#### `if()` statement

```R
if (condition) {true.expression} else {false.expression}

# EXAMPLE
if(is.vector('How are you?')) print('Good') else print('Bad')		# returns "Good"
if(is.numeric('How are you?')) print('Good') else print('Bad')	# returns "Bad"
```



* Multiple conditions and cases

```R
if(condition1 && condition2) {expression}		# AND operator
if(condition1 || condition2) {expression}		# OR operator
```

```R
if(case1) {expression}
else if(case2) {expression}
	...
else {expression}
```



#### `ifelse()` statement

> Vectorized version of the `if()` statement. If an element passes condition as TRUE, ifelse() returns the corresponding value of expression1; otherwise, it returns expression2.

```R
ifelse(condition, expression1, expression2)

# EXAMPLE 1
x <- 123
ifelse(x==123, "correct", "wrong")

# ExAMPLE 2
y <- c(1, 3, 5)
ifelse(y < 2, "small",
      ifelse(y > 4, "big", "middle"))
```



#### `switch()` statement

> The switch() function is an alternative to multiple use of the if() function. The switch() function accepts as its first argument an expression:
>
> - If the expression is character object, it is compared to the remaining arguments until a match is found. The value of the matched argument is returned.
> - If the first argument is an integer in the range (1:nargs– 1), it is compared to the remaining arguments until a match is found.  The value of the matched argument is returned.

```R
# EXAMPLE 1 (character)
switch("c",
      a="apple", b="banana", c="carrot", d="durian")		# returns "carrot"


# EXAMPLE 2 (character, english to german dictionary function)
en2gr <- function(en) {
  switch(en, 
         'one'   = 'eins',
         'two'   = 'zwei',
         'three' = 'drei',
         'four'  = 'vier'
  )
}
english = 'one'
sapply(english, en2gr)


# EXAMPLE 3 (integer)
require(stats)
centre <- function(x, type) {
  switch(type,
         mean = mean(x),
         median = median(x),
         trimmed = mean(x, trim = .1))
}
x <- rcauchy(10)
centre(x, "mean")
centre(x, "median")
centre(x, "trimmed")


# EXAPMLE 4 (integer, switch combined with if statements for score to grade conversion)
score <- sample(0:100, 1)		# get random integer between 0 and 100 

if(score>=90) { 
  grade = 1
} else if (score>=80) {
  grade = 2
} else if (score>=70) {
  grade = 3
} else if (score>=60) {
  grade = 4
} else{
  grade = 5
}

level <- switch(grade,"A", "B", "C", "D", "F")
cat(score, " corresponds to \"", level,"\" in grade.", sep='')
```





## 2. Loops in R (for, while, repeat)

#### `for` loop

> a loop that has to run statements or a set of statements multiple times. For loop is commonly used to iterate over items of a sequence.

```R
for (value in sequence) { statement }

# EXAMPLE 1 (print from 1 to 3)
for (val in 1:3) { 
    print(val) 
}  

# EXAMPLE 2 (display days of a week)
week <- c('Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday') 
   
for (day in week) { 
    print(day) 
} 
```



#### `while` loop

> a type of control statement which will run a statement or a set of statements repeatedly unless the given condition becomes false.

```R
while (condition) { statement }

# EXAMPLE 1 (same result as the example 1 of for loop)
cnt = 1
while (cnt <= 3) {
  print(cnt)
  cnt = cnt+1
}
```



#### `repeat` loop

> a simple loop that will run the same statement or a group of statements repeatedly until the stop condition has been encountered.

```R
repeat 
{ 
   statement
  
   if( condition ) { break }
}
```

```R
# EXAMPLE with break (same result as the example 1 of for loop and while loop)
val = 1

repeat {
    print(val) 
    val = val + 1
      
    if(val > 3)  { break } 
} 
```

```R
# EXAMPLE with next (skip a particular iteration in loop)
for (val in 1:3) { 
    if (val == 2) { next }
    
    print(val) 
} 
```

