# compiler_design_practice

2025 - 2 semester, practice for compiler design with cool language 
---------------------------------------------------------------------------------------

* class definition 
```
class <type> [inherits <type> { <feature_list>}
```

* feature _list 
> can be local variable or method, variable can access only using method.

* example 
```
 class Cons inherits List {
     xcar : Int;
     xcdr : List;
     isNull() : Bool {false};
     init(hd : Int, tl:List ) : Cons {
          {
              xcar <- hd;
              xcdr <- tl;
              self;  // return value 
           }
     }
>
};
```
>we can use init method by using 
``` 
let c : Cons <- (new Cons).init(1,some_list)
```
> new : make new type object , <- : assign value same with "=" in other languages


* class inheritance 
> 1. only one inheritance allowed 
> 2. parent class must be implemented in same code block
> 3. Default class - if we don't inheritance any class - is "Object" which is root class 
> 4. child class always can use 

* Methods
> 1. Methods can have several parameters which must must declare type.
> 2. when you inherit class P into class c, you can use the method f which declared in class P.
> 3. But you must return same Type both P and C


* Expressions : how to use method
 ```
 class Animal {
   speak() : {"..."};
 }
 class dog {
  speak() : {"wak wak" };
 }
 let a : Animal <-new Dog in
 ```
 1. 
 ```
 let a : Animal = <- new Dog in
 a.speak();
 ```
 2. 
 ```
 (new Dog).speak();
 ```
 3. 
 ```
 let a : Animal = <-new Dog in 
 a@animal.speak();
 ```
a@animal.speak() call parent method. 

* Condition
  ```
  if condition then result1 else result2 fi
  ```
  Result's type is the intersection type of both "result1" and "result2"
  for example, type of result 1 is dog and result2 is cat then return type is animal(if cat and dog inherits animal)

*Block 
> Block's type is determined by last value written.
```
{
let x : Int <- 5 in x+2;
let y : String <- "hi" in y;
}
```
Type of Block is String 

* Let
You ONLY use "x" "in x+2" expression. It is similar to closure in Rust.
```
{
let x : Int <- 5 in x+2;
let y : String <- "hi" in y;
}
```
Because cool is expression language.


* Case : 
  estimate type and execute code line that has same type. 
  ```
  case a of
  x : Int => x+1;
  y : String => y.concat("!");
  ```
  ```
  case a of
  x : Dog => x.speak();
  y : Cat => y.speak();
  ```



