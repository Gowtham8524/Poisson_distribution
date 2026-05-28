# Fitting Poisson  distribution
EXP NO :02

DATE   :27/04/2026 

NAME   :Gowtham S

REG NO :212224100018
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  
Python and Visual component tool
# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.
![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)
 Conditions for Poisson Distribution:
1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 

# Procedure :
![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)
# Program :
```
import math
from scipy.stats import chi2
data = list(map(int, input("Enter data: ").split()))
N = len(data)
max_x = max(data)
obs = [data.count(x) for x in range(max_x + 1)]
mean = sum(x * obs[x] for x in range(len(obs))) / N
chi_sq = 0
print("x  Obs  Exp")
for x in range(len(obs)):
    p = math.exp(-mean) * (mean ** x) / math.factorial(x)
    exp = N * p
    if exp > 0:
        chi_sq += (obs[x] - exp) ** 2 / exp
    print(x, obs[x], round(exp, 2))
df = max_x - 1
critical = chi2.ppf(0.99, df)
print("\nChi-square =", round(chi_sq, 2))
print("Critical =", round(critical, 2))
if chi_sq < critical:
    print("Fits Poisson")
else:
    print("Not Fit")
```
# Output : 

<img width="1378" height="302" alt="image" src="https://github.com/user-attachments/assets/34094998-3647-41e1-916f-37d3046c1eb5" />
# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 

# link:
https://github.com/Gowtham8524/Poisson_distribution

 
