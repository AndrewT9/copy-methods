# Performance Comparison of Array Copying Methods
This document compares the performance of various methods used to copy arrays in JavaScript. The methods are evaluated based on their execution times and efficiency. The times are measured in terms of the "complexity" (denoted as c) with different factors.

## Device specification:
Processor: 11th Gen Intel(R) Core(TM) i7-11370H @ 3.30GHz   3.30 GHz
RAM: 16.0 GB
System type: 64-bit operating system, x64-based processor

```javascript

// For Loop - Time 2.5c - 3c
const m = [];
for (let t = 0; t < arr.length; t++) {
    m.push(arr[t]);
}

// While Loop - Time 2.5c - 3.25c 
const m = [];
let k = 0;
while (k < arr.length) {
    m.push(arr[k]);
    k++;
}

// map() - Time 1c - 1.2c 
const m = arr.map(item => item);

// filter() - Time 2.7c - 2.8c 
const m = arr.filter(item => true);

// Using Spread Operator - Time 19.4c - 21.4c 
const m = [...arr];

// Using Array.from() Method - Time 15.7c - 16.1c
const m = Array.from(arr);

// Using JSON.parse(JSON.stringify()) - Time 17.1c - 17.5c
const m = JSON.parse(JSON.stringify(arr));

// Using slice() Method - Time 1.3c - 5.9c
const m = arr.slice();


# Summary of Performance

| Method                            | Time Complexity (relative to array length) |
|-----------------------------------|--------------------------------------------|
| **For Loop**                      | 2.5c - 3c                                  |
| **While Loop**                    | 2.5c - 3.25c                               |
| **`map()`**                       | 1c - 1.2c                                  |
| **`filter()`**                    | 2.7c - 2.8c                                |
| **Spread Operator (`[...]`)**     | 19.4c - 21.4c                              |
| **`Array.from()`**                | 15.7c - 16.1c                              |
| **`JSON.parse(JSON.stringify())`**| 17.1c - 17.5c                              |
| **`slice()`**                     | 1.3c - 5.9c                                |
