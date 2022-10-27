# Big O Notation

# Notes
 * is not exact
 * generalized way to understand how an alg will react as it's inputs grow
 * helps us understand why or why not to use a certain data structure


remember, these are not exactly concrete, more general points

- Growth is with respect to input
   - look for loops
- constants are dropped
  0 (2N) => 0 (N)

  take for example
  n = 1; O(10N) = 10; O(N^2) = 1;
  n = 5; O(10N) = 50; O(N^2) = 25;
  n = 100; O(10N) = 1,000; O(N^2) = 10,000;
   
The much more heinous issue here is the N^2, not necessarily that N can be large. It implies the algorithm is doing Too Much.

Remeber tho there are practical differences. Even if O(100N) is faster than O(N^2), it could still win in a some of cases with smaller data sets.

- you're probably looking for the worst case


*there are other ways to measure time vs space complexity, but Big O is the easiest way to measure the "upper bound"

## Examples

### O(N^2)

really just squaring it - for every single character, during the interaction, we're going through every single character.

Like, two loops for each singular input. 

```
function sum (nums: number[]) {
    let sum;

    for (let n = 0; n < nums.length; n++) { // one loop
        for (let j = 0; j < nums.length; n++ ) { // two loop
            sum += num;
        }
    }

    return sum;
}
```

### O(N^3)

an extension of the above, for every input, go through every input, and through every input - three times through every single input.

starting to see why exponents matter more than constants.

Say `nums` has a length of 50. That's not heinous until you consider there are 150 operations in the alg before its finished. Even worse if `nums` has an even greater length. A real world example could be much, much worse.

```
function sum (nums: number[]) {
    let sum;

    for (let n = 0; n < nums.length; n++) { // one loop
        for (let j = 0; j < nums.length; n++ ) { // two loop
            for (let q = 0; q < nums.length; n++) { // look three
                sum += num;
            }
        }
    }

    return sum;
}
```

### O(n log n)

"quicksort" is apparently an example - revisit when you know what tf that is

"half the amount of space needed to search by going through once"

go through N characters > reduce size > repeat

```
// needs example :(
```

### O(log n)

"binary search trees" for example - again, revisit when you understand what those words mean together

"half the amount of input you need to look at, but only look at one point at a time"
