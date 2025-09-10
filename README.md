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

