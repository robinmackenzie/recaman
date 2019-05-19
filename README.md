# Recamán sequence
## Definitions
Useful links
* [OEIS](https://oeis.org/A005132)
* [Wolfram](http://mathworld.wolfram.com/RecamansSequence.html)
* [Popular Numberphile video](https://www.youtube.com/watch?v=FGC5TdIiT9U)

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
