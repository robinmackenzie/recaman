# Recamán sequence
## Definitions
Useful links:
* [Popular Numberphile video](https://www.youtube.com/watch?v=FGC5TdIiT9U)
* [OEIS](https://oeis.org/A005132)
* [Wolfram](http://mathworld.wolfram.com/RecamansSequence.html)
* [p5.js implementation as an online coding challenge](https://www.youtube.com/watch?v=DhFZfzOvNTU)

The sequence for e.g. first 10 iterations is: 1, 3, 6, 2, 7, 13, 20, 12, 21, 11

## Javascript implementation
```javascript
function recaman(iterations) {
  let sequence = [];
  let index = 0;
  for (let n=1; n<=iterations; n++) {
    sequence.push(index);
    let candidate = index - n;
    (candidate >= 0 & sequence.indexOf(candidate) < 0) ? index = candidate : index += n;
  }
  return sequence;
}
```

## Why do a visualisation?
The Numberphile video is a good summary of this question. The sequence exhibits, in the words of Alex Bellos:
*"... an interesting clash between order and chaos... "*

## This visualisation
The implementation in the repository builds on a number of nice-to-have requirements:
* Let the user decide the number of iterations to visualise
* Let the user pan and zoom the resulting visualisation
* Add some colour to the visualisation as an aid to interpretation
* Per the comments on the youtube video on the p5.js implementation, show where an arc hits a prime number

To do features:
* Show where the arc hits a number from another sequence e.g. Fibonacci, Lucas
* Colorise based on something other than iteration index
* Highlight an arc and see the generating items of the sequence

