## Question:

Terminal: `Ubuntu`  
Command:  
```sh

    Have the function BracketCombinations(num) read num which will be an integer greater than or equal to zero, and return the number of valid combinations that can be formed with num pairs of parentheses. For example, if the input is 3, then the possible combinations of 3 pairs of parenthesis, namely: ()()(), are ()()(), ()(()), (())(), ((())), and (()()). There are 5 total combinations when the input is 3, so your program should return 5.

    # Examples
    # Input: 3
    # Output: 5
    # Input: 2
    # Output: 2

    function BracketCombinations(num) { 
        // code goes here  
        return num; 
    }
    // keep this function call here 
    console.log(BracketCombinations(readline()));
```

**Solutions:**

Terminal: `Ubuntu`  
Command:  
```sh

    function factorial(n) {
        if (n === 0 || n === 1) return 1;
        let result = 1;
        for (let i = 2; i <= n; i++) {
            result *= i;
        }
        return result;
    }

    function BracketCombinations(num) {
        if (num === 0) return 1; // Base case: one valid combination for 0 pairs
        // Calculate the nth Catalan number
        const c = factorial(2 * num) / (factorial(num + 1) * factorial(num));
        return c;
    }

    // keep this function call here
    console.log(BracketCombinations(3)); // Output: 5
    console.log(BracketCombinations(2)); // Output: 2
    console.log(BracketCombinations(0)); // Output: 1
```

## Question:

Terminal: `Ubuntu`  
Command:  
```sh

    Min Window Substring
    Have the function MinWindowSubstring(strArr) take the array of strings stored in strArr, which will contain only two strings, the first parameter being the string N and the second parameter being a string K of some characters, and your goal is to determine the smallest substring of N that contains all the characters in K. For example: if strArr is ["aaabaaddae", "aed"] then the smallest substring of N that contains the characters a, e, and d is "dae" located at the end of the string. So for this example your program should return the string dae.

    Another example: if strArr is ["aabdccdbcacd", "aad"] then the smallest substring of N that contains all of the characters in K is "aabd" which is located at the beginning of the string. Both parameters will be strings ranging in length from 1 to 50 characters and all of K's characters will exist somewhere in the string N. Both strings will only contains lowercase alphabetic characters.
    Examples

    Input: ["ahffaksfajeeubsne", "jefaa"]
    Output: aksfaje
    Input: ["aaffhkksemckelloe", "fhea"]
    Output: affhkkse

    example code
    function MinWindowSubstring(strArr) { 
        // code goes here  
        return strArr; 
    }
    
    // keep this function call here 
    console.log(MinWindowSubstring(readline()));
```

**Solutions:**

Terminal: `Ubuntu`  
Command:  
```sh

   function MinWindowSubstring(strArr) {

        const N = strArr[0]; // The main string
        const K = strArr[1]; // The string containing characters to include
        const charCount = {}; // To keep track of required characters
        const windowCount = {}; // To keep track of characters in the current window

        let left = 0; // Left pointer for the sliding window
        let minLength = Infinity; // To store the length of the minimum window
        let minSubstring = ""; // To store the minimum window substring
        let required = K.length; // Total number of characters we need to match

        // Count characters in K
        for (let char of K) {
            charCount[char] = (charCount[char] || 0) + 1;
        }

        for (let right = 0; right < N.length; right++) {
            const currentChar = N[right];
            // Update the window count
            if (charCount[currentChar]) {
                windowCount[currentChar] = (windowCount[currentChar] || 0) + 1;
                // If we have matched the required characters
                if (windowCount[currentChar] <= charCount[currentChar]) {
                    required--;
                }
            }

            // Try to contract the window until it's no longer valid
            while (required === 0) {
                const windowSize = right - left + 1;
                if (windowSize < minLength) {
                    minLength = windowSize;
                    minSubstring = N.substring(left, right + 1);
                }

                const leftChar = N[left];
                // Update the window count and required characters
                if (charCount[leftChar]) {
                    windowCount[leftChar]--;
                    if (windowCount[leftChar] < charCount[leftChar]) {
                        required++;
                    }
                }
                left++; // Move the left pointer to the right
            }
        }

        return minSubstring;
    }

    // keep this function call here
    console.log(MinWindowSubstring(["ahffaksfajeeubsne", "jefaa"])); // Output: aksfaje
    console.log(MinWindowSubstring(["aaffhkksemckelloe", "fhea"])); // Output: affhkkse
```

## Question:

Terminal: `Ubuntu`  
Command:  
```sh

    Tree Constructor
    Have the function TreeConstructor(strArr) take the array of strings stored in strArr, which will contain pairs of integers in the following format: (i1,i2), where i1 represents a child node in a tree and the second integer i2 signifies that it is the parent of i1. For example: if strArr is ["(1,2)", "(2,4)", "(7,2)"], then this forms the following tree:


    which you can see forms a proper binary tree. Your program should, in this case, return the string true because a valid binary tree can be formed. If a proper binary tree cannot be formed with the integer pairs, then return the string false. All of the integers within the tree will be unique, which means there can only be one node in the tree with the given integer value.

    Examples
    Input: ["(1,2)", "(2,4)", "(5,7)", "(7,2)", "(9,5)"]
    Output: true
    Input: ["(1,2)", "(3,2)", "(2,12)", "(5,2)"]
    Output: false

```

**Solutions:**

Terminal: `Ubuntu`  
Command:  
```sh

    function TreeConstructor(strArr) {
    const childCount = {};
    const parentCount = {};

    for (const pair of strArr) {
        const [child, parent] = pair.slice(1, -1).split(',').map(Number);

        // Count how many parents each child has
        parentCount[child] = (parentCount[child] || 0) + 1;

        // If a child has more than 1 parent, return false
        if (parentCount[child] > 1) {
            return false;
        }

        // Count how many children each parent has
        childCount[parent] = (childCount[parent] || 0) + 1;

        // If a parent has more than 2 children, return false
        if (childCount[parent] > 2) {
            return false;
        }
    }

    // Count root nodes (those not in the childCount)
    const rootCount = Object.keys(childCount).filter(parent => !parentCount[parent]).length;

    // There must be exactly one root for a valid tree
    return rootCount === 1;
}

```

## Question:

Terminal: `Ubuntu`  
Command:  
```sh

    Bracket Matcher
    Have the function BracketMatcher(str) take the str parameter being passed and return 1 if the brackets are correctly matched and each one is accounted for. Otherwise return 0. For example: if str is "(hello (world))", then the output should be 1, but if str is "((hello (world))" the the output should be 0 because the brackets do not correctly match up. Only "(" and ")" will be used as brackets. If str contains no brackets return 1.
    Examples
    Input: "(coder)(byte))"
    Output: 0
    Input: "(c(oder)) b(yte)"
    Output: 1

    my code
    function BracketMatcher(str) { 

    // code goes here  
    return str; 

    }
    
    // keep this function call here 
    console.log(BracketMatcher(readline()));

```

**Solutions:**

Terminal: `Ubuntu`  
Command:  
```sh

    function BracketMatcher(str) {
        let count = 0;

        for (const char of str) {
            if (char === '(') {
                count++;
            } else if (char === ')') {
                count--;
            }

            // If count goes negative, we have a mismatch
            if (count < 0) {
                return 0;
            }
        }

        // At the end, count should be zero if all brackets are matched
        return count === 0 ? 1 : 0;
    }

    // Keep this function call here 
    console.log(BracketMatcher(readline()));  // Example input: "(coder)(byte))"

```

## Question:

Terminal: `Ubuntu`  
Command:  
```sh

    Codeland Username Validation
    Have the function CodelandUsernameValidation(str) take the str parameter being passed and determine if the string is a valid username according to the following rules:

    1. The username is between 4 and 25 characters.
    2. It must start with a letter.
    3. It can only contain letters, numbers, and the underscore character.
    4. It cannot end with an underscore character.

    If the username is valid then your program should return the string true, otherwise return the string false.
    Examples
    Input: "aa_"
    Output: false
    Input: "u__hello_world123"
    Output: true

```

**Solutions:**

Terminal: `Ubuntu`  
Command:  
```sh

    function CodelandUsernameValidation(str) {
        const length = str.length;

        // Rule 1: Length must be between 4 and 25
        if (length < 4 || length > 25) {
            return "false";
        }

        // Rule 2: Must start with a letter
        if (!/^[a-zA-Z]/.test(str)) {
            return "false";
        }

        // Rule 3: Can only contain letters, numbers, and underscores
        if (!/^[a-zA-Z0-9_]+$/.test(str)) {
            return "false";
        }

        // Rule 4: Cannot end with an underscore
        if (str[length - 1] === '_') {
            return "false";
        }

        return "true";  // If all checks pass, return true
    }

    // Keep this function call here 
    console.log(CodelandUsernameValidation(readline()));  // Example input

```

## Question:

Find Intersection
Have the function FindIntersection(strArr) read the array of strings stored in strArr which will contain 2 elements: the first element will represent a list of comma-separated numbers sorted in ascending order, the second element will represent a second list of comma-separated numbers (also sorted). Your goal is to return a comma-separated string containing the numbers that occur in elements of strArr in sorted order. If there is no intersection, return the string false.
Examples
Input: ["1, 3, 4, 7, 13", "1, 2, 4, 13, 15"]
Output: 1,4,13
Input: ["1, 3, 9, 10, 17, 18", "1, 4, 9, 10"]
Output: 1,9,10

Solution 5

function FindIntersection(strArr) {
    // Split the input strings and convert to arrays of numbers
    const arr1 = strArr[0].split(',').map(num => parseInt(num.trim(), 10));
    const arr2 = strArr[1].split(',').map(num => parseInt(num.trim(), 10));

    // Convert arrays to sets
    const set1 = new Set(arr1);
    const set2 = new Set(arr2);

    // Find intersection
    const intersection = [...set1].filter(num => set2.has(num));

    // If there's no intersection, return "false"
    if (intersection.length === 0) {
        return "false";
    }

    // Return the intersection as a comma-separated string
    return intersection.join(',');
}

// Keep this function call here 
console.log(FindIntersection(readline()));  // Example input


Question 6

Questions Marks
Have the function QuestionsMarks(str) take the str string parameter, which will contain single digit numbers, letters, and question marks, and check if there are exactly 3 question marks between every pair of two numbers that add up to 10. If so, then your program should return the string true, otherwise it should return the string false. If there aren't any two numbers that add up to 10 in the string, then your program should return false as well.

For example: if str is "arrb6???4xxbl5???eee5" then your program should return true because there are exactly 3 question marks between 6 and 4, and 3 question marks between 5 and 5 at the end of the string.
Examples
Input: "aa6?9"
Output: false
Input: "acc?7??sss?3rr1??????5"
Output: true

Solution 6

function QuestionsMarks(str) {
    let lastNum = -1; // To store the last number found
    let questionCount = 0; // To count question marks
    let foundPair = false; // To track if any pair that sums to 10 was found

    for (let i = 0; i < str.length; i++) {
        const char = str[i];

        // If the character is a digit
        if (char >= '0' && char <= '9') {
            const currentNum = parseInt(char);

            // If we have found a previous number
            if (lastNum !== -1) {
                // Check if the two numbers sum to 10
                if (lastNum + currentNum === 10) {
                    foundPair = true;
                    // Check if there are exactly 3 question marks between them
                    if (questionCount !== 3) {
                        return "false";
                    }
                }
            }
            // Reset the question mark count
            questionCount = 0; 
            lastNum = currentNum; // Update the lastNum
        } else if (char === '?') {
            // Count question marks
            questionCount++;
        }
    }

    // Return false if no pairs that sum to 10 were found
    return foundPair ? "true" : "false";
}

// Keep this function call here 
console.log(QuestionsMarks(readline()));  // Example input


Question 7

First Reverse
Have the function FirstReverse(str) take the str parameter being passed and return the string in reversed order. For example: if the input string is "Hello World and Coders" then your program should return the string sredoC dna dlroW olleH.
Examples
Input: "coderbyte"
Output: etybredoc
Input: "I Love Code"
Output: edoC evoL I

my code
function FirstReverse(str) { 

  // code goes here  
  return str; 

}
   
// keep this function call here 
console.log(FirstReverse(readline()));

Solution 7

function FirstReverse(str) {
    // Split the string into an array, reverse it, and join it back into a string
    return str.split('').reverse().join('');
}

// Keep this function call here 
console.log(FirstReverse(readline()));  // Example input


Question 8

First Factorial
Have the function FirstFactorial(num) take the num parameter being passed and return the factorial of it. For example: if num = 4, then your program should return (4 * 3 * 2 * 1) = 24. For the test cases, the range will be between 1 and 18 and the input will always be an integer.
Examples
Input: 4
Output: 24
Input: 8
Output: 40320

my code
function FirstFactorial(num) { 

  // code goes here  
  return num; 

}
   
// keep this function call here 
console.log(FirstFactorial(readline()));

Solution 8
function FirstFactorial(num) {
    let factorial = 1;
    
    // Calculate factorial iteratively
    for (let i = 1; i <= num; i++) {
        factorial *= i;
    }
    
    return factorial;
}

// Keep this function call here 
console.log(FirstFactorial(readline()));  // Example input

Question 9

Longest Word
Have the function LongestWord(sen) take the sen parameter being passed and return the longest word in the string. If there are two or more words that are the same length, return the first word from the string with that length. Ignore punctuation and assume sen will not be empty. Words may also contain numbers, for example "Hello world123 567"
Examples
Input: "fun&!! time"
Output: time
Input: "I love dogs"
Output: love

my code
function LongestWord(sen) { 

  // code goes here  
  return sen; 

}
   
// keep this function call here 
console.log(LongestWord(readline()));

Solution 9

function LongestWord(sen) {
    // Remove punctuation and split the string into words
    const words = sen.replace(/[^\w\s]/g, '').split(/\s+/);
    
    let longestWord = '';

    // Find the longest word
    for (const word of words) {
        if (word.length > longestWord.length) {
            longestWord = word;
        }
    }

    return longestWord;
}

// Keep this function call here 
console.log(LongestWord(readline()));  // Example input

Question 10

React Button Toggle
We provided some simple React template code. Your goal is to modify the component so that you can properly toggle the button to switch between an ON state and an OFF state. When the button is on and it is clicked, it turns off and the text within it changes from ON to OFF and vice versa. Make use of component state for this challenge.

You are free to add classes and styles, but make sure you leave the component ID's and classes provided as they are. Submit your code once it is complete and our system will validate your output.

MY CODE
import React, { useState } from 'react';
import { createRoot } from 'react-dom/client';

function Toggle() {
  function handleClick() {
    // todo
  }
  
  return (
    <button>ON</button>
  );
}

const container = document.getElementById('root');
const root = createRoot(container);
root.render(<Toggle />);


Solution 10

import React, { useState } from 'react';
import { createRoot } from 'react-dom/client';

function Toggle() {
  // Initialize the state with 'ON'
  const [isOn, setIsOn] = useState(true);

  // Handle button click
  function handleClick() {
    setIsOn(prevState => !prevState); // Toggle the state
  }
  
  return (
    <button onClick={handleClick}>
      {isOn ? 'ON' : 'OFF'}
    </button>
  );
}

const container = document.getElementById('root');
const root = createRoot(container);
root.render(<Toggle />);
