#1. Функція add2(x, y), яка повертає суму двох чисел.
```r
add2 <- function(x, y){
  return(x + y)
}
> add2(1,2)
[1] 3
```
#2. Функція above(x, n), яка приймає вектор та число n, та повертає всі елементі вектору, які більше n. По замовчуванню n = 10.
```r
addabove <- function(x, n) {
  return(x[x>n])
}
> addabove(c(1,3,7,5,12,2,6), 4)
[1]  7  5 12  6
```
#3. Функція my_ifelse(x, exp, n), яка приймає вектор x, порівнює всі його елементи за допомогою exp з n, та повертає елементи вектору, які відповідають умові expression. Наприклад, my_ifelse(x, “>”, 0) повертає всі елементи x, які більші 0. Exp може дорівнювати “<”, “>”, “<=”, “>=”, “==”. Якщо exp не співпадає ні з одним з цих виразів, повертається вектор x.
```r
my_ifelse <-function(x, exp, n) {
  if (exp==">") {
    return(x[x>n])
  }  else if (exp=="<") {
    return(x[x<n])
  }  else if (exp=="<=") {
    return(x[x<=n])
  }  else if (exp==">=") {
    return(x[x>=n])
  }  else if (exp=="==") {
    return(x[x==n])
  }  else {
    return(x)
  }
}
> my_ifelse(c(1,3,2,6,7,4,3),">=",3)
[1] 3 6 7 4 3
```
**#4. Функція columnmean(x, removeNA), яка розраховує середнє значення (mean) по кожному стовпцю матриці, або data frame. Логічний параметр removeNA вказує, чи видаляти NA значення. По замовчуванню він дорівнює TRUE.**
```r
columnmean<-function(x,removeNA=TRUE){
  apply(x,2,mean,na.rm=removeNA)
}

columnmean(df)
   x    y 
2.75 6.50 
> columnmean(df, FALSE)
 x  y 
NA NA
```
