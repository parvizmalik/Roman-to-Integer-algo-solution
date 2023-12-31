﻿# Roman-to-Integer-algo-solution
The code provided is a solution to convert a Roman numeral string into its corresponding integer value. I will explain how this algorithm works with an example, and prove its correctness.

**Algorithm Logic:**

1. Create a dictionary `m` to map each Roman numeral to its corresponding integer value.
2. Initialize `ans` as 0. This will store the final integer value.
3. Iterate through the string `s`:
   - If the current numeral is smaller than the next numeral, subtract its value from `ans`. This handles cases where a smaller numeral precedes a larger numeral, like "IV" (4) or "XC" (90).
   - Otherwise, add the numeral's value to `ans`.
4. Return `ans`.

**Example:**

Let's use the Roman numeral "MCMXCIV" which corresponds to the integer 1994.

- **M**: Add 1000 to `ans` → `ans = 1000`
- **C**: Since C (100) is smaller than the next numeral, M (1000), subtract 100 from `ans` → `ans = 900`
- **M**: Add 1000 to `ans` → `ans = 1900`
- **X**: Since X (10) is smaller than the next numeral, C (100), subtract 10 from `ans` → `ans = 1890`
- **C**: Add 100 to `ans` → `ans = 1990`
- **I**: Since I (1) is smaller than the next numeral, V (5), subtract 1 from `ans` → `ans = 1989`
- **V**: Add 5 to `ans` → `ans = 1994`

At the end of the loop, the `ans` is 1994 which is the integer representation of the Roman numeral "MCMXCIV".

**Proof of Correctness:**

1. **Invariant**: After each loop iteration, the variable `ans` contains the correct integer representation of the processed part of the string.
   
2. **Base Case**: Before the loop starts, no part of the string is processed, and `ans` is 0, so the invariant holds.
   
3. **Induction Step**: Let's assume that after processing `s[i]`, the invariant holds. When we process `s[i+1]`, we either add its value or subtract it based on its relation to `s[i]`. This mirrors the logic of Roman numerals, ensuring the invariant is maintained.

By the time the loop finishes processing the entire string, the invariant guarantees that `ans` contains the correct integer representation of the string, thus proving the algorithm's correctness.
