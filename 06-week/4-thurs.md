# Thursday June 1 

## Warm Up

* [Partial application](https://repl.it/student/submissions/1067552)

Solution: 

```
function partial(fn) {
  return function f1(...f1innerArgs) {
    if (f1innerArgs.length >= fn.length) {
      return fn(...f1innerArgs);
    } else {
      return function f2(...f2innerArgs) {
        return f1(...f1innerArgs.concat(f2innerArgs));
      };
    }
  };
}
```

## Solo Project

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

