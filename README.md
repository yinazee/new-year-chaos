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


