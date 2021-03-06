

# Control structures in R

These allow you to control the flow of execution of a script typically inside of a function.
Common ones include:

* if, else
* for
* while
* repeat
* break
* next
* return

We don't use these while working with R interactively but rather inside functions. 

## If


```r
if(condition) {
    # do something 
} else { 
    # do something else
}
```
e.g. 




```r
x <- 1:15
if(sample(x, 1) <= 10) {
    print("x is less than 10") 
} else {
    print("x is greater than 10")
}
```

**Vectorization with ifelse**


```r
ifelse(x <= 10, "x less than 10", "x greater than 10")
```

Other valid ways of writing if/else


```r
if(sample(x,1) < 10) {
    y <- 5
} else {
    y <- 0
}
```


```r
y <- if(sample(x,1) < 10) {
 5
} else {
    0
}
```

## for

A `for` loop works on an iterable variable and assigns successive values till the end of a sequence.


```r
for(i in 1:10) {
    print(i)
}
```


```r
x <- c("apples", "oranges", "bananas", "strawberries")

for(i in x) {
    print(x[i])
}

for(i in 1:4) {
    print(x[i])
}

for(i in seq(x)) {
    print(x[i])
}

for(i in 1:4) print(x[i])
```

## Nested loops



```r
m <- matrix(1:10, 2)
for(i in seq(nrow(m))) {
    for(j in seq(ncol(m))) {
        print(m[i,j])
}
}
```

## While


```r
i <- 1
while(i < 10) {
    print(i)
    i <- i + 1
}
```

Be sure there is a way to exit out of a `while` loop.

## Repeat and break


```r
repeat {
    # simulations; generate some value
    # have an expectation
    # if within some range, then exit the loop
    if((value - expectation) <= threshold) {
    break
}
}
```


## Next


```r
for(i in 1:20) {
    if(i %%2 ==1) {
        next
    } else { 
        print(i)
        }
}
```

This loop will only print even numbers and skip over odd numbers. Later we'll learn other functions that will help us avoid these types of slow control flows as much as possible (mostly the `while` and `for` loops).




