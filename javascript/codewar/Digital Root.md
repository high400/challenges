Digital root is the recursive sum of all the digits in a number.

Given n, take the sum of the digits of n. 
If that value has more than one digit, continue reducing in this way until a single-digit number is produced. 
The input will be a non-negative integer.

Answer: 
This one was wrong.

                    function digital_root(n) {
                      var digits = n.toString().split("").map(Number);
                      var sum = 0;
                      for (var i = 0; i < digits.length; i++) {
                        sum += digits[i];
                      }
                      var sumString = sum.toString();
                      if (sumString.length > 1) {
                        var sumDigits = sumString.split("").map(Number);
                        var firstSumDigit = sumDigits.slice(0);
                        var lastSumDigit = sumDigits.slice(-1);
                        return firstSumDigit[0] + lastSumDigit[0];
                      } else {
                          return sum;
                      }
                    }
                    
 This one is the CORRECT ONE:
 
                    function digital_root(n){
                    let result = 0;
                    n.toString().split('').map (n => {
                    result += Number(n)
                    })
                    return result > 9 ? digital_root(result) : result;
                    }
