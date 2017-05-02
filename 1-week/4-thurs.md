# Thursday April 27

## Warm Up
[Music Decoder](https://www.codewars.com/kata/a-simple-music-decoder)

* Parse number, range, or multiple

### Regular Expressions

* `(/\s*,\s*/)` remove spaces `\s` around the comma
* `(/^\-?\d+$/)` look for - or no - in front of any # of digits
* to match particular character in regular expression, need a backslash before the literal: `\*`
* then you have to put whole thing between `/ /` : so `/\*/`
* `"hello".match(/ll/)` => `["ll",2,"hello"]`
* `"t*m".match(/\*/)` => `["*",1,"t*m"]`
* `match` returns 
	* an array with `[matched segment, index it starts at, and original string]` if found
	* otherwise returns `null`

## [HTML Canvas](https://github.com/rithmschool/intermediate_javascript/blob/master/unit-01/04-introduction-to-canvas.md)

* [Canvas experiments](https://code.tutsplus.com/articles/21-ridiculously-impressive-html5-canvas-experiments--net-14210)

## [Shapes Game!](https://github.com/rithmschool/intermediate_javascript_exercises/tree/master/canvas_exercise/shapes_game)

* Check out mine on my personal site [here](http://shriyanevatia.com/shapes_game/index.html)

## Turning Shapes Game into Tap Tap Revolution
* Transform up arrow indices by flipping x and y coordinates across the relevant axes i.e. 90 degree rotation is flip across x=y (on normal coordinate plane; this one is diff with (0,0) in upper left)
	* Remove the rotation crap
* Only clear screen up to y = 650px (right above 4 bottom arrows) each time a new arrow is drawn
* But still clear entire screen when game is over
* Add neon border around arrows
* Get each arrow to fall at random rate (within fast range)
* Update score logic for clicking within 5px (or less) of target
* Add glow CSS around arrow when near target (and stronger glow when **exactly** on target)
* Add patterned background for whole game
* Add way to get +5 for perfect, +3 for great, +1 for good

#### Above and Beyond
* Get free game song and match arrows drawn to game rhythm

************************************

## Questions 

* 

## Ideas & Notes

* 

## To Do

* Music Decoder codewars exercise
* Figure out how to draw text on the HTML canvas
* 

## Coming up this week

* 





