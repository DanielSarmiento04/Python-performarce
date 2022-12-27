# Optimize Code - Python

## Hardware

1. macbook air 2020 m1 156 ram

## Software

1. python 3.10.8
2. MacOs Monterrey 12..6


This repository has been designed to compare the performance from different code versions (with the same result) and comparing

1. Legibility
2. Speed
3. Ram Usage

For this purpose, I have decided to implement an algorithm that with a any number (integer), the algorithm find all the prime number up to this number.

## Concepts

A prime number is a natural number (integer) greater than 1 that is no a product of 2 smaller numbers


## Conclusion

Python is a declarative programming language. IN this way, the faster result is implement numpy-numba with 1.1 seconds. The slowest result was more than 1 min.

```python
num = 1_000_000
numbers = np.arange(0, num, dtype=np.int32)
```


```python
@njit
def is_prime(number:int) -> bool:
    arr = np.arange(2, int(np.sqrt(number))+1)
    return not np.any(number%arr == 0)

primes = numbers[is_prime(numbers)]
```

- best performance
```python
@vectorize([boolean(int8),
            boolean(int16),
            boolean(int32),
            boolean(int64),
            ])
def is_prime(number):
    arr = np.arange(2, int(np.sqrt(number))+1)
    return not np.any(number%arr == 0)
primes = numbers[is_prime(numbers)]
```



## References
- [Wikipedia](https://en.wikipedia.org/wiki/Prime_number)
- [optimize prime Function](https://geekflare.com/prime-number-in-python/)