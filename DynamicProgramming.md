# Dynamic Programming

## Idea

* DP table
  * dp[i] = function(dp[i-1])
  * dimension -- states  ==. dp[i] precisely describe the result of overall problem

## Implementation Paradigm

1. Recursion: dp(n) = max(dp(n-1)..)
2. Memorization, hash table, avoid repeated computation, Top-Bottom approach
3. Loop, dp table[i] <= dp table[i-1], bottom-top approach
4. N, dp table[N+1], dp_i = dp_i-1 + dp_i-2
