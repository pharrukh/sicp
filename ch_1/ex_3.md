# Упражнение 1.3.
Определите процедуру, которая принимает в качестве аргументов три числа и возвращает сумму
квадратов двух больших из них.

```scheme

    (define (<= a b) (or (< a b) (= a b)))
    (define (>= a b) (or (> a b) (= a b)))
    (define (square a) (* a a))
    (define (min a b) (if (<= a b) a b))
    (define (max a b) (if (>= a b) a b))
    (define (get-first-max a b c) 
        (max (max a b) (max b c))
    )
    (define (get-second-max a b c) 
        (min (max a b) (max b c))
    )
    (define (sum-of-squares-of-two-max a b c) 
            (+
                (square (get-first-max a b c))
                (square (get-second-max a b c))
            )
    )

    (sum-of-squares-of-two-max 1 2 3)
    (sum-of-squares-of-two-max 4 2 3)
```