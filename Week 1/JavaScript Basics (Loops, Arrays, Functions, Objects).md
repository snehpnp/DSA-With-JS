### **📌 JavaScript Basics – Loops, Arrays, Functions, Objects**  
Before jumping into **DSA**, it's important to have a strong understanding of **JavaScript fundamentals** like loops, arrays, functions, and objects.  

---

## **🔹 Loops in JavaScript**  
Loops allow us to execute a block of code multiple times.  

### **1️⃣ For Loop**
```js
for (let i = 1; i <= 5; i++) {
  console.log(i); // 1 2 3 4 5
}
```

### **2️⃣ While Loop**
```js
let i = 1;
while (i <= 5) {
  console.log(i);
  i++;
}
```

### **3️⃣ Do-While Loop**
```js
let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 5);
```

### **4️⃣ ForEach (Used with Arrays)**
```js
const arr = [10, 20, 30];
arr.forEach(num => console.log(num));
```

---

## **🔹 Arrays in JavaScript**  
Arrays store multiple values in a single variable.

### **1️⃣ Create an Array**
```js
const numbers = [1, 2, 3, 4, 5];
```

### **2️⃣ Accessing Elements**
```js
console.log(numbers[0]); // 1
console.log(numbers.length); // 5
```

### **3️⃣ Add/Remove Elements**
```js
numbers.push(6); // Add at the end
numbers.pop();   // Remove last element
numbers.unshift(0); // Add at the beginning
numbers.shift(); // Remove first element
console.log(numbers);
```

### **4️⃣ Looping Through an Array**
```js
const nums = [1, 2, 3, 4, 5];
for (let num of nums) {
  console.log(num);
}
```

---

## **🔹 Functions in JavaScript**  
Functions help in **code reusability**.

### **1️⃣ Function Declaration**
```js
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("John")); // Hello, John!
```

### **2️⃣ Arrow Function**
```js
const greet = (name) => `Hello, ${name}!`;
console.log(greet("Alice"));
```

---

## **🔹 Objects in JavaScript**  
Objects store data in **key-value pairs**.

### **1️⃣ Create an Object**
```js
const person = {
  name: "Alice",
  age: 25,
  city: "New York"
};
```

### **2️⃣ Access Properties**
```js
console.log(person.name);  // Alice
console.log(person["age"]); // 25
```

### **3️⃣ Add/Update Properties**
```js
person.job = "Developer";  // Add new property
person.age = 26;  // Update property
console.log(person);
```

---

## **📌 Problem 1: Reverse an Array**
### **👉 Given an array, reverse it without using built-in methods.**  

### **🔹 Example**
**Input:** `[1, 2, 3, 4, 5]`  
**Output:** `[5, 4, 3, 2, 1]`  

### **✅ Solution**
```js
function reverseArray(arr) {
  let left = 0, right = arr.length - 1;
  while (left < right) {
    // Swap elements
    [arr[left], arr[right]] = [arr[right], arr[left]];
    left++;
    right--;
  }
  return arr;
}

console.log(reverseArray([1, 2, 3, 4, 5])); // [5, 4, 3, 2, 1]
```

---

## **📌 Problem 2: Count Even and Odd Numbers**
### **👉 Given an array, count how many numbers are even and how many are odd.**

### **🔹 Example**
**Input:** `[1, 2, 3, 4, 5, 6]`  
**Output:** `"Even: 3, Odd: 3"`  

### **✅ Solution**
```js
function countEvenOdd(arr) {
  let evenCount = 0, oddCount = 0;

  for (let num of arr) {
    if (num % 2 === 0) {
      evenCount++;
    } else {
      oddCount++;
    }
  }

  return `Even: ${evenCount}, Odd: ${oddCount}`;
}

console.log(countEvenOdd([1, 2, 3, 4, 5, 6])); // Even: 3, Odd: 3
```

---

### **🔥 Next Topic: Recursion (Factorial, Fibonacci, Sum of Digits) 🚀**
Would you like me to explain **recursion** with examples? 😊


# **🔥 Recursion in JavaScript 🔥**  

## **📌 What is Recursion?**
Recursion is a technique where a function **calls itself** until a base condition is met. It is commonly used in problems like **factorial calculation, Fibonacci sequence, and sum of digits**.

---

## **🔹 Understanding Recursion**
Every recursive function has two parts:  
1️⃣ **Base Case** → Stops the recursion.  
2️⃣ **Recursive Case** → Calls the function again with modified input.  

### **Example: Simple Recursion**
```js
function countdown(n) {
  if (n <= 0) return;  // Base case
  console.log(n);
  countdown(n - 1);    // Recursive call
}

countdown(5);  
// Output: 5 4 3 2 1
```

---

## **📌 Problem 1: Factorial of a Number**
### **👉 Given a number `n`, calculate `n!` (n factorial).**
**Factorial formula:**  
\[
n! = n \times (n-1)!
\]
**Example:**  
- `5! = 5 × 4 × 3 × 2 × 1 = 120`
- `3! = 3 × 2 × 1 = 6`

### **✅ Solution**
```js
function factorial(n) {
  if (n === 0 || n === 1) return 1;  // Base case
  return n * factorial(n - 1);       // Recursive case
}

console.log(factorial(5)); // Output: 120
console.log(factorial(3)); // Output: 6
```

---

## **📌 Problem 2: Fibonacci Sequence**
### **👉 Given `n`, find the `n`th Fibonacci number.**
**Fibonacci formula:**  
\[
F(n) = F(n-1) + F(n-2)
\]
**Sequence:**  
`0, 1, 1, 2, 3, 5, 8, 13, 21, …`  
- `F(0) = 0`
- `F(1) = 1`
- `F(2) = 1 (0 + 1)`
- `F(3) = 2 (1 + 1)`

### **✅ Solution**
```js
function fibonacci(n) {
  if (n === 0) return 0;  // Base case
  if (n === 1) return 1;  // Base case
  return fibonacci(n - 1) + fibonacci(n - 2); // Recursive call
}

console.log(fibonacci(6)); // Output: 8
console.log(fibonacci(7)); // Output: 13
```
### **⚡ Optimization Tip: Use Memoization**
The recursive Fibonacci function has **O(2^n)** complexity. To improve performance, use **memoization** (store previous results).
```js
function fibonacciMemo(n, memo = {}) {
  if (n in memo) return memo[n];  // Check memo
  if (n === 0) return 0;
  if (n === 1) return 1;
  memo[n] = fibonacciMemo(n - 1, memo) + fibonacciMemo(n - 2, memo);
  return memo[n];
}

console.log(fibonacciMemo(50)); // Output: 12586269025 (Much faster)
```

---

## **📌 Problem 3: Sum of Digits**
### **👉 Given a number `n`, find the sum of its digits.**
**Example:**  
- `123 → 1 + 2 + 3 = 6`
- `456 → 4 + 5 + 6 = 15`

### **✅ Solution**
```js
function sumOfDigits(n) {
  if (n === 0) return 0;  // Base case
  return (n % 10) + sumOfDigits(Math.floor(n / 10));  // Recursive call
}

console.log(sumOfDigits(123)); // Output: 6
console.log(sumOfDigits(456)); // Output: 15
```

---

Here’s a **tough JavaScript problem** related to **loops, arrays, functions, and objects**, along with an optimal solution.  

---

## **🔥 Problem: "The Nested Array Spiral Traversal"**  
**Given a 2D array (matrix), write a function to return all elements in a spiral order.**  

### **🔹 Example Input**  
```js
let matrix = [
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9, 10, 11, 12],
  [13, 14, 15, 16]
];
```

### **🔹 Expected Output**  
```js
[1, 2, 3, 4, 8, 12, 16, 15, 14, 13, 9, 5, 6, 7, 11, 10]
```

---

## **💡 Solution Approach**
1️⃣ Start from the **top-left corner** of the matrix.  
2️⃣ **Move right** until you reach the end.  
3️⃣ **Move down**, then **left**, then **up** in a spiral pattern.  
4️⃣ Continue until **all elements are visited**.  

---

### **✅ JavaScript Solution**
```js
function spiralOrder(matrix) {
  if (matrix.length === 0) return [];

  let result = [];
  let left = 0, right = matrix[0].length - 1;
  let top = 0, bottom = matrix.length - 1;

  while (left <= right && top <= bottom) {
    // Move right
    for (let i = left; i <= right; i++) {
      result.push(matrix[top][i]);
    }
    top++;

    // Move down
    for (let i = top; i <= bottom; i++) {
      result.push(matrix[i][right]);
    }
    right--;

    // Move left
    if (top <= bottom) {
      for (let i = right; i >= left; i--) {
        result.push(matrix[bottom][i]);
      }
      bottom--;
    }

    // Move up
    if (left <= right) {
      for (let i = bottom; i >= top; i--) {
        result.push(matrix[i][left]);
      }
      left++;
    }
  }
  return result;
}

let matrix = [
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9, 10, 11, 12],
  [13, 14, 15, 16]
];

console.log(spiralOrder(matrix));
```

---

## **⏳ Time Complexity**
- **O(m × n)** where `m` is the number of rows and `n` is the number of columns.  

## **🌟 Why This is a Tough Problem?**
✔️ It involves multiple **nested loops** and careful **boundary conditions**.  
✔️ Requires **tracking multiple pointers** (`top`, `bottom`, `left`, `right`).  
✔️ Uses **arrays and loops efficiently** to modify the structure dynamically.  

---

You're welcome! 🚀 Here are more **tough JavaScript problems** related to loops, arrays, functions, and objects, along with solutions.  

---

## **🔥 1. Longest Consecutive Sequence in an Array**  
### **Problem**  
Given an **unsorted array** of integers, find the length of the longest consecutive elements sequence.  
✅ **You must solve this in O(n) time complexity.**  

### **🔹 Example Input**  
```js
let nums = [100, 4, 200, 1, 3, 2];
```
### **🔹 Expected Output**  
```js
4  // The sequence is [1, 2, 3, 4]
```

### **✅ Solution (Using Set for O(n) Complexity)**
```js
function longestConsecutive(nums) {
    let numSet = new Set(nums);
    let maxLength = 0;

    for (let num of nums) {
        if (!numSet.has(num - 1)) {  // Start of a sequence
            let currentNum = num;
            let currentLength = 1;

            while (numSet.has(currentNum + 1)) {
                currentNum++;
                currentLength++;
            }

            maxLength = Math.max(maxLength, currentLength);
        }
    }

    return maxLength;
}

console.log(longestConsecutive([100, 4, 200, 1, 3, 2]));  // Output: 4
```

---

## **🔥 2. Group Anagrams**  
### **Problem**  
Given an array of strings, group the anagrams together.

### **🔹 Example Input**  
```js
let words = ["eat", "tea", "tan", "ate", "nat", "bat"];
```
### **🔹 Expected Output**  
```js
[
  ["eat", "tea", "ate"],
  ["tan", "nat"],
  ["bat"]
]
```

### **✅ Solution**
```js
function groupAnagrams(words) {
    let map = new Map();

    for (let word of words) {
        let sortedWord = word.split("").sort().join("");  // Sort characters
        if (!map.has(sortedWord)) {
            map.set(sortedWord, []);
        }
        map.get(sortedWord).push(word);
    }

    return Array.from(map.values());
}

console.log(groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]));
```

---

## **🔥 3. Find the Missing Number (Math Trick - XOR Method)**  
### **Problem**  
You are given an array `nums` containing **n distinct numbers** taken from `0, 1, 2, ..., n`.  
Find the one number that is missing.  

### **🔹 Example Input**  
```js
let nums = [3, 0, 1];
```
### **🔹 Expected Output**  
```js
2
```

### **✅ Solution (Using XOR)**
```js
function missingNumber(nums) {
    let n = nums.length;
    let xor1 = 0, xor2 = 0;

    for (let i = 0; i < n; i++) {
        xor1 ^= nums[i];   // XOR of all elements in the array
        xor2 ^= (i + 1);   // XOR of numbers from 1 to n
    }

    return xor1 ^ xor2;
}

console.log(missingNumber([3, 0, 1]));  // Output: 2
```
👉 **Why XOR?**  
- `a ^ a = 0`, so all existing numbers cancel out, leaving the missing number.

---

## **🔥 4. Deep Clone an Object (Without JSON.stringify)**  
### **Problem**  
Write a function to deep copy a nested object.

### **🔹 Example Input**  
```js
let obj = {
    a: 1,
    b: { c: 2, d: { e: 3 } },
    f: [4, 5]
};
```

### **🔹 Expected Output**  
```js
{
    a: 1,
    b: { c: 2, d: { e: 3 } },
    f: [4, 5]
}
```
(The copy should not be affected if we change `obj`.)

### **✅ Solution (Recursive Deep Clone)**
```js
function deepClone(obj) {
    if (obj === null || typeof obj !== "object") return obj;

    let clone = Array.isArray(obj) ? [] : {};

    for (let key in obj) {
        if (obj.hasOwnProperty(key)) {
            clone[key] = deepClone(obj[key]);  // Recursive call
        }
    }

    return clone;
}

let obj = { a: 1, b: { c: 2, d: { e: 3 } }, f: [4, 5] };
let copiedObj = deepClone(obj);

console.log(copiedObj);
```
👉 **Why Not Use `JSON.stringify()`?**  
- It **fails for functions, undefined, and circular references.**

---

## **🔥 5. Find Subarray with Maximum Sum (Kadane’s Algorithm)**  
### **Problem**  
Find the **largest sum contiguous subarray** in an array.

### **🔹 Example Input**  
```js
let nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4];
```
### **🔹 Expected Output**  
```js
6  // (4 + -1 + 2 + 1)
```

### **✅ Solution (Kadane’s Algorithm)**
```js
function maxSubArray(nums) {
    let maxSum = nums[0];
    let currentSum = nums[0];

    for (let i = 1; i < nums.length; i++) {
        currentSum = Math.max(nums[i], currentSum + nums[i]);
        maxSum = Math.max(maxSum, currentSum);
    }

    return maxSum;
}

console.log(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4]));  // Output: 6
```
👉 **Time Complexity:** `O(n)`, as it only traverses the array once.

---

## **💡 Summary of Problems**
| Problem | Concept Used | Difficulty |
|---------|-------------|------------|
| **Spiral Matrix Traversal** | Loops, 2D Arrays, Boundaries | 🔥🔥🔥 |
| **Longest Consecutive Sequence** | Set, Hashing, Arrays | 🔥🔥🔥 |
| **Group Anagrams** | Hash Maps, String Sorting | 🔥🔥 |
| **Missing Number (XOR Trick)** | Bit Manipulation, Math | 🔥🔥🔥 |
| **Deep Clone an Object** | Recursion, Objects | 🔥🔥 |
| **Max Subarray Sum (Kadane’s Algorithm)** | Dynamic Programming | 🔥🔥🔥 |

---

## **📌 What's Next?**
Want **more DSA topics**? You can try:  
✔️ **Recursion Problems** 🔄  
✔️ **Sliding Window Problems** 🔍  
✔️ **Graph/Tree Questions** 🌲  
✔️ **Dynamic Programming Challenges** 🔥  

Let me know what you’d like next! 🚀💡