# Anagramic-Squares
from math import ceil, sqrt, floor
from collections import defaultdict
def hash(s): return tuple(str(s).count(str(d)) for d in range(10))

N = int(input())
start, end = ceil(sqrt(10 ** (N - 1))), floor(sqrt(10 ** N))
freq, max_count, ans = defaultdict(int), 0, 0

for i in range(start, end + 1):
    h = hash(i * i)
    freq[h] += 1
    if freq[h] > max_count:
        max_count, ans = freq[h], i * i

print(ans)	
