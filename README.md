# Recamán sequence
## Definitions
> Recamán's sequence (or Recaman's sequence): a(0) = 0; for n > 0, a(n) = a(n-1) - n if positive and not already in the sequence, otherwise a(n) = a(n-1) + n. 
>
> -- <cite>[OEIS](https://oeis.org/A005132)</cite>

The sequence for e.g. first 10 iterations is: 1, 3, 6, 2, 7, 13, 20, 12, 21, 11

Useful links:
* [Popular Numberphile video](https://www.youtube.com/watch?v=FGC5TdIiT9U)
* [Wolfram](http://mathworld.wolfram.com/RecamansSequence.html)
* [p5.js implementation as an online coding challenge](https://www.youtube.com/watch?v=DhFZfzOvNTU)

## Demo
https://robinmackenzie.github.io/recaman/

Here is an example with 66 iterations of the sequence with primes highlighted. The prime highlight colors an arc red where the destination index is prime.

![](recaman1.png)

Here is an example with 400 iterations of the sequence using D3's interpolateWarm scale. The visualisation has been panned and zoomed to show detail around indices 30-150.

![](recaman2.PNG)

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
The Numberphile video is a good summary of this question. The sequence exhibits, in the words of [Alex Bellos](http://www.alexbellos.com/):
> "... an interesting clash between order and chaos... "

## This visualisation
The implementation builds on a number of ideas arising from the Numberphile video:
* Let the user 'play' with the graph with pan and zoom
* Let the user decide the number of iterations to visualise
* Add some colour to the visualisation as an aid to interpretation
* Per the comments on the youtube video on the p5.js implementation, show where an arc hits a prime number

To do features:
* Show where the arc hits a number from another sequence e.g. Fibonacci
* Colorise based on something other than iteration index
* Highlight an arc and see the generating items of the sequence
* Investigate 'un-fixing' the x-axis when panning on y-axis



