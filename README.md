# kotlin-hourglass-sum-2Darray
Maximum sum of hour glass in matrix

Given a  2D Array, A:

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
0 0 0 0 0 0
```
Print the largest (maximum) hourglass sum found in A

Sample Input

```
1 1 1 0 0 0
0 1 0 0 0 0
1 1 1 0 0 0
0 0 2 4 4 0
0 0 0 2 0 0
0 0 1 2 4 0
```

Sample Output

19

Kotlin Code Function:

```
fun hourGlassSum2DArray(arr: Array<Array<Int>>): Int {

    // As the value range starts from -9 and the total hours glass has 7 elements so I have taken int maxSum = -9*7 = -63;
    var maxSum = -9 * 7
    var counterSum = 0

    //Through a simple calculation, from an NxN matrix, there are
    //(N-2)*(N-2) hourglasses. Hence, all you have to do is to find N-2   and replace the i<4 and j<4 to i<N-2 and j<N-2 respectively.
    // Rows are i, Columns are j


    for (i in 0 until arr.size - 2) {
        for (j in 0 until arr.size - 2) {
            counterSum =
                arr[i][j] + arr[i][j + 1] + arr[i][j + 2] + arr[i + 1][j + 1] + arr[i + 2][j] + arr[i + 2][j + 1] + arr[i + 2][j + 2]
            maxSum = Math.max(maxSum, counterSum)

        }
    }
    return maxSum
}
```
