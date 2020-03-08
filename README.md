# new-year-chaos
HackerRank Challenge - Javascript

……………q = [1 2 5 3 7 8 6 4]
original order = 1 2 3 4 5 6 7 8

```
function minimumBribes(queue) {
     let chaotic = false
     let bribes = 0
     for (let i = 0; i < queue.length; i++) {
        if (queue[i] - (i+1) > 2) { chaotic = true }
          for (let j = queue[i] - 2; j < i; j++) {
            if (queue[j] > queue[i]) { bribes++ }
          }
        }
     if(chaotic === true){
     console.log("Too chaotic")
     } else {
     console.log(bribes)
     }
}
```

Here is how the logic will play out. Keep track of i and j.
i = 0
q = 1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
j = -1
q[j] = N/A and q[i] = 1, since j < i is true, j++
j = 0 q[j] = 1 and q[i] = 1 since 1 > 1 is false and j < i is not true, stops.
— — — —
now i = 1
q = 1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
j = 0
q[j] = 1 and q[i] = 2 since 1 > 2 is false and j < i is true, j++
j = 1
q[j] = 2 and q[i] = 2 since j < i is not true, stops.
— — — —
now i = 2
1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
j = 3
q[j] = 3 and q[i] = 5 since 3 > 5 is false and j < i is not true, stops.
— — — —
now i = 3
1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
now j = 1
q[j] = 2 and q[i] = 3 since 2 > 3 is false and j < i is true, j++
now j = 2
q[j] = 5 and q[i] = 3 since 5 > 3 is true and j < i is true, bribe++ and j++
now j = 3 q[j] = 3 and q[i] = 3 since 3 > 3 is false and j < i is not true, stops.
— — — —
now i = 4
1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
now j = 5
q[j] = 8 and q[i] = 7 since 8 > 7 is true and j < i is not true, bribe++ and stops.
— — — —
now i = 5
q = 1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
j = 6 q[j] = 6 and q[i] = 8 since 6 > 8 is false and j < i is not true, stops.
— — — —
now i = 6
1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
j = 4
q[j] = 7 and q[i] = 6 since 7 > 6 is true and j < i is true, bribes++ and j++
j = 5
q[j] = 8 and q[i] = 6 since 8 > 6 is true and j < i is true, bribes++ and j++
j = 6
q[j] = 6 and q[i] = 6 since 6 > 6 is false and j < i is not true, stops.
— — — —
now i = 7
q = 1, 2, 5, 3, 7, 8, 6, 4
j = queue[i] — 2
j = 2
q[j] = 5 and q[i] = 4 since 5 > 4 is true and j < i is true, bribes++ and j++
now j = 3
q[j] = 3 and q[i] = 4, since 3 > 4 is false and j < i is true, j++
now j = 4
q[j] = 7 and q[i] = 4, since 7 > 4 is true and j < i is true, bribes++ and j++
now j = 5
q[j] = 8 and q[i] = 4, since 8 > 4 is true and j < i is true, bribes++ and j++
now j = 6
q[j] = 6 and q[i] = 4, since 6 > 4 is true and j < i is true, bribes++ and j++
now j = 7
q[j] = 4 and q[i] = 4, since 4 > 4 is false and j < i is not true, stops.






