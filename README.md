# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM
To simulate and compare Huffman Coding and Shannon-Fano Coding techniques for data compression using MATLAB or Scilab, and evaluate their efficiency based on average code length and entropy.


# SOFTWARE REQUIRED
scilab

# ALGORITHMS
1. Start
2. Input symbols and their probabilities.
3. Sort symbols:
         Huffman: Ascending order.
         Shannon-Fano: Descending order.
4. Generate codewords:
        Huffman: Combine smallest probabilities until one node remains.
        Shannon-Fano: Split list recursively with near-equal probabilities.
5. Calculate entropy, average length, efficiency, and redundancy.
6. Display results.
7. End


# PROGRAM
```python
import numpy as np

import math

L = 0

hs = 0

p = []

lk = []

n = int(input("Enter the number of Samples : "))

for i in range (n):

pr = float(input(f"Enter the probability of sample values {i + 1}: "))  

p.append(pr)
for i in range (n):

l = float(input(f"Enter the length of the sample values {i + 1}: "))  

lk.append(l)
for k in range (n):

Avg1 = p[k] * lk[k]

L = L + Avg1
for k in range (n):

e = p[k] * math.log(1 / p[k], 2)

hs = hs + e
hs = round(hs,3)

eff = hs / L

eff = round(eff,3)

red = round(1 - eff,3)

var = 0

for k in range(n):

var1 = p[k] * (lk[k]-L)**2

var = var + var1

var = round(var,3)

print(f"Average Codeword Length is : {L}")

print(f"Entropy is : {hs}")

print(f"Efficiency is : {eff * 100}%")

print(f"Redudancy is : {red}")

print(f"Variance is : {var}")    import numpy as np

import math

L = 0

hs = 0

p = []

lk = []

n = int(input("Enter the number of Samples : "))

for i in range (n):

pr = float(input(f"Enter the probability of sample values {i + 1}: "))  

p.append(pr)
for i in range (n):

l = float(input(f"Enter the length of the sample values {i + 1}: "))  

lk.append(l)
for k in range (n):

Avg1 = p[k] * lk[k]

L = L + Avg1
for k in range (n):

e = p[k] * math.log(1 / p[k], 2)

hs = hs + e
hs = round(hs,3)

eff = hs / L

eff = round(eff,3)

red = round(1 - eff,3)

var = 0

for k in range(n):

var1 = p[k] * (lk[k]-L)**2

var = var + var1

var = round(var,3)

print(f"Average Codeword Length is : {L}")

print(f"Entropy is : {hs}")

print(f"Efficiency is : {eff * 100}%")

print(f"Redudancy is : {red}")

print(f"Variance is : {var}")
```



# OUTPUT
![image](https://github.com/user-attachments/assets/736d3029-9d19-48b7-80d7-c9a3a7b21b9e)


Average Codeword Length is : 2.625

Entropy is : 2.625

Efficiency is : 100.0%

Redudancy is : 0.0

Variance is : 0.484


 
# RESULT
The simulation successfully generated the prefix codes using both Huffman and Shannon-Fano algorithms for the given set of symbols and their probabilities.
It was observed that:

Huffman Coding generally provides a slightly better or optimal average code length.

Shannon-Fano Coding is simpler but may not always result in the most efficient code.

The average code length was compared with the entropy of the source to evaluate the efficiency of both methods.
