# Wednesday May 31

## Warm Up

* [Powerset Problem](https://www.codewars.com/kata/simple-fun-number-273-powerset/train/javascript)
* Still need to work on binary and bitshift problems

```
function powerset(nums) {
  var powerset = [];
  for (var i = 0; i < Math.pow(2, nums.length); i++) {
    var iBaseTwo = i.toString(2);
    while (iBaseTwo.length < nums.length) iBaseTwo = '0' + iBaseTwo;
    var subset = [];
    for (var j = 0; j < nums.length; j++) {
      if (iBaseTwo[j] === '1') subset.push(nums[j])
    }
    powerset.push(subset);
  } 
  return powerset;
}
```

## Solo Projects Continued

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* 

## Coming up this week

* 

