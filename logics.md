# Programming Logics

## Check Even or Odd

### JavaScript Logic

```javascript
// Function to check if a number is even or odd
function checkEvenOrOdd(number) {
    if (number % 2 === 0) {
        return 'Even';
    } else {
        return 'Odd';
    }
}

// Example usage
const result1 = checkEvenOrOdd(10);
console.log(`10 is ${result1}`); // Output: "10 is Even"

const result2 = checkEvenOrOdd(7);
console.log(`7 is ${result2}`); // Output: "7 is Odd"
