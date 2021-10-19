---
title: "FUNCTION IN R (EXERCISES)"
date: 2020-09-16 10:45:00 -0400
categories:
  - 
---


# Function in R (Exercises)
> <h6> R 함수의 정의와 활용 연습문제 </h6>




## Exercise 1: create 'exam1' function which returns a vector "Aa" "Bb" ... "Zz".
> <h6> "Aa" "Bb" ... "Zz" 등으로 구성된 벡터를 리턴하는 함수를 생성한다. (매개변수 없음, 리턴 값 1개)</h6>

```R
exam1 <- function() {
  return(paste0(LETTERS, letters))
}

exam1()
```



## Exercise 2: create 'exam2' function which returns the sum of 1 to an input number 'n'.
> <h6>1 부터 매개변수로 받은 숫자 값까지의 합을 구해서 리턴하는 함수를 생성한다. (매개변수 1개, 리턴 값 1개)</h6>

```R
exam2 <- function(num) {
  return((num * (num + 1)) / 2)
}

exam2(10)
```



## Exercise 3: create 'exam3' function which returns the difference between two input numbers.
> <h6>매개변수로 받은 두 숫자 중 큰 값에서 작은 값의 차를 리턴하는 함수를 생성한다. 두 값이 동일하면 0을 리턴한다. (매개변수 2개, 리턴 값 1개)</h6>

```R
exam3 <- function(num1, num2) {
  if (num1 != num2) { return(max(num1, num2) - min(num1, num2)) }
  else { return(0) }
}

exam3(2,5)
```



## Exercise 4: create 'exam4' function for arithmetic operations.
> <h6>매개변수로 두 숫자와 연산자를 받아 연산을 수행하는 함수를 생성한다. 연산자는 +, -, *, %/%, %%로 한정하며, %/%와 %%가 전달된 경우에 한해서 오류1, 오류2 케이스를 지정한다. (매개변수 3개, 리턴 값 1개)</h6>

```R
exam4 <- function(num1, oper, num2) {
  if (!(oper %in% c('+', '-', '*', '%/%', '%%'))) {
    return("Please enter proper operators")
  }
  
  else if (oper %in% c('%/%', '%%')) {
    if (num1 == 0) { return('Error 1') }
    else if (num2 == 0) { return('Error 2') }
    else {
      if (oper == '%/%') { return(num1%/%num2) }
      if (oper == '%%') { return(num1%%num2) }
    }
  }
  
  else {
    if (oper == '+') { return(num1+num2) }
    if (oper == '-') { return(num1-num2) }
    if (oper == '*') { return(num1*num2) }
  }
}

exam4(15,'%/%',5)
```



## Exercise 5: create 'exam5' function that prints an input character for n times.
> <h6>매개변수로 숫자와 문자를 입력받아 숫자의 개수만큼 문자를 출력하는 함수를 생성한다. 문자가 전달되지 않으면 기본값은 "#"로 처리하며, 숫자로 음의 값이 전달되면 아무것도 출력하지 않는다. (매개변수 2개, 리턴 값 없음)</h6>

```R
exam5 <- function(num, char='#') {
  paste(rep(char, num), collapse = "")
}

exam5(5)
```



## Exercise 6: create 'exam6' function that converts score to grade.
> <h6>매개변수로 학생의 점수를 받아 등급을 출력하는 함수를 생성한다. NA값이 존재하는 경우엔 처리 불가를 출력한다. (매개변수 1개, 리턴 값 없음)</h6>

```R
exam6 <- function(...) {
  score <- c(...)

  for (i in score) {
    if (is.na(i)) {grade <- 'NA'}
    else {
      if (i>=85) {grade <- 'HIGH'}
      else if (i>=70) {grade <- 'MIDDLE'}
      else {grade <- 'LOW'}
    }
    print(paste(i,' is equivalent to ', grade, sep=''))
  }
}

exam6(10,75,90,NA)
```


## More Exercise Codes on my github
[github.com/letsgititdana/R_exercises](https://github.com/letsgititdana/R_exercises)
