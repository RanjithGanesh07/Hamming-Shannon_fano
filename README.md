# Huffman-Shannon_Fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano coding techniques to this source. 
Draw the tree diagram and compute the average codeword length, entropy, variance, redundancy, and efficiency.


**Name:** Ranjith Ganesh B  **Reg No:** 212223060222

## Aim:
To implement Huffman and Shannon-Fano coding for the given source probabilities and analyze their performance metrics.

## Tools Required:
- Python with NumPy and SciPy libraries.
- Google Colab

## Program:
```python
# Huffman and Shannon-Fano Coding
import numpy as np
import math 

L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples: "))

for i in range(n): 
    pr = float(input(f"Enter the probability of sample {i + 1}: "))  
    p.append(pr)

for j in range(n): 
    l = float(input(f"Enter the length of sample {j + 1}: "))  
    lk.append(l)

# Average Codeword Length
for k in range(n):
    Avg1 = p[k] * lk[k]
    L += Avg1

# Entropy Calculation
for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs += e
hs = round(hs, 3)

# Efficiency Calculation
eff = round(hs / L, 3)

# Redundancy Calculation
red = round(1 - eff, 3)

# Variance Calculation
var = 0
for k in range(n):
    var1 = p[k] * (lk[k] - L) ** 2
    var += var1
var = round(var, 3)

print(f"Average Codeword Length: {L}")
print(f"Entropy: {hs}")
print(f"Efficiency: {eff}")
print(f"Redundancy: {red}")
print(f"Variance: {var}")
```

## Calculation:
The computation involves constructing Huffman and Shannon-Fano trees, determining codeword lengths, and evaluating key metrics.

### Tree Diagrams:
![shannon_page-0001](https://github.com/user-attachments/assets/b93c0268-b2b5-4885-a8b0-24fa86760403)

![shannon_page-0002](https://github.com/user-attachments/assets/6ee4ac6a-6998-442c-9ebe-1cb89763f984)

![shannon_page-0003](https://github.com/user-attachments/assets/aec463a2-483f-44e8-91a9-58bc6e756b93)

![shannon_page-0004](https://github.com/user-attachments/assets/2eeee077-ac00-405f-a6a6-4402bd241952)


## Output:
![image](https://github.com/user-attachments/assets/b29bb8bd-bb68-48b3-921f-cbea6a850874)

## Results:
The Huffman and Shannon-Fano coding techniques have been successfully applied to the given source. The average codeword length, entropy, variance, redundancy, and efficiency have been computed.
