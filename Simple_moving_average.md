https://rosettacode.org/wiki/Averages/Simple_moving_average

```
// Not good enough
// Should use repeat
Mean(Vector...) = Vector.sum/Vector.count
Capture(Vector..., k, period) = if(
    period >= k,
    Vector.take(k),
    Vector.skip(k-period).take(period)
)
Sma(Vector..., period) = {
UpdatedVectorMean(k) = Capture(Vector, k, period).Mean
Output = range(1, Vector.count).map(UpdatedVectorMean)
}

List = 1, 2, 3, 2, 7
Sma(List, 3)
```

Output:
```
1
1.5
2
2.3333333333333333333333333333
4
```
