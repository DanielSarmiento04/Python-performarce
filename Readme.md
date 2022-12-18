# Optimize Code - Python

This repository has been designed to compare the performance from different code versions (with the same result) and comparing

1. Legibility
2. Speed
3. Ram Usage

For this purpose, I have decided to implement an algorithm that with a any number (integer), the algorithm find all the prime number up to this number.

## Concepts

A prime number is a natural number (integer) greater than 1 that is no a product of 2 smaller numbers


## Conclusion

Python is a declarative programming language. IN this way, the faster result is implement numpy-numba with 0.9 seconds. The slowest result was more than 1 min.

```python
@njit
def is_prime(number:int) -> bool:
    arr = np.arange(2, int(np.sqrt(number))+1)
    return not np.any(number%arr == 0)

primes = np.array(list(filter(is_prime, numbers)))
```



## References
(Wikipedia)[https://en.wikipedia.org/wiki/Prime_number]
(optimize prime Function)[https://geekflare.com/prime-number-in-python/]