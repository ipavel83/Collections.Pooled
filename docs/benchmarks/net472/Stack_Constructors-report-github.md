``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0

Job=Clr  Runtime=Clr  

```
|                       Method |      N |   Type |           Mean |         Error |        StdDev |         Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |------- |------- |---------------:|--------------:|--------------:|---------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackICollectionConstructor** |   **1000** |    **Int** |       **331.8 us** |      **3.557 us** |      **3.327 us** |       **331.4 us** |  **1.00** |    **0.00** |   **1290.0391** |           **-** |           **-** |          **3968.97 KB** |
| PooledICollectionConstructor |   1000 |    Int |     1,106.1 us |     34.389 us |     35.315 us |     1,089.3 us |  3.34 |    0.12 |     11.7188 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 |    Int |     7,884.6 us |    161.000 us |    142.722 us |     7,859.1 us | 23.79 |    0.52 |   2687.5000 |           - |           - |          8274.68 KB |
| PooledIEnumerableConstructor |   1000 |    Int |     9,714.4 us |     72.958 us |     56.960 us |     9,708.2 us | 29.28 |    0.37 |     31.2500 |           - |           - |           117.25 KB |
|                              |        |        |                |               |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |   **1000** | **String** |       **885.0 us** |     **16.395 us** |     **12.800 us** |       **878.9 us** |  **1.00** |    **0.00** |   **2556.6406** |           **-** |           **-** |          **7876.88 KB** |
| PooledICollectionConstructor |   1000 | String |     2,809.5 us |     57.234 us |     47.793 us |     2,795.9 us |  3.17 |    0.07 |     11.7188 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 | String |    13,286.1 us |     41.661 us |     38.970 us |    13,278.3 us | 15.01 |    0.23 |   5281.2500 |           - |           - |         16271.19 KB |
| PooledIEnumerableConstructor |   1000 | String |    20,175.8 us |    136.070 us |    113.625 us |    20,214.6 us | 22.80 |    0.40 |     31.2500 |           - |           - |           125.25 KB |
|                              |        |        |                |               |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** |    **Int** |     **3,408.5 us** |     **67.978 us** |    **186.089 us** |     **3,319.2 us** |  **1.00** |    **0.00** |  **12656.2500** |           **-** |           **-** |         **39210.66 KB** |
| PooledICollectionConstructor |  10000 |    Int |    15,240.4 us |    301.644 us |    699.106 us |    14,891.9 us |  4.46 |    0.23 |           - |           - |           - |            39.25 KB |
|  StackIEnumerableConstructor |  10000 |    Int |    79,826.6 us |  1,584.985 us |  2,004.499 us |    78,956.2 us | 22.10 |    1.07 |  41571.4286 |           - |           - |        128520.07 KB |
| PooledIEnumerableConstructor |  10000 |    Int |   105,986.0 us |    557.855 us |    521.818 us |   105,876.1 us | 29.44 |    1.78 |           - |           - |           - |           118.05 KB |
|                              |        |        |                |               |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** | **String** |     **8,775.9 us** |     **31.162 us** |     **27.625 us** |     **8,774.0 us** |  **1.00** |    **0.00** |  **24984.3750** |           **-** |           **-** |         **78371.88 KB** |
| PooledICollectionConstructor |  10000 | String |    37,675.5 us |    974.631 us |    911.670 us |    37,273.5 us |  4.30 |    0.11 |           - |           - |           - |            39.43 KB |
|  StackIEnumerableConstructor |  10000 | String |   214,142.3 us |  4,255.016 us |  8,299.083 us |   209,862.1 us | 24.17 |    0.95 |  41333.3333 |  41333.3333 |  41333.3333 |        256378.94 KB |
| PooledIEnumerableConstructor |  10000 | String |   226,563.2 us |  1,332.660 us |  1,181.368 us |   227,040.1 us | 25.82 |    0.17 |           - |           - |           - |           125.33 KB |
|                              |        |        |                |               |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** |    **Int** |    **84,141.4 us** |  **1,655.209 us** |  **2,265.669 us** |    **83,185.5 us** |  **1.00** |    **0.00** |  **32000.0000** |  **30666.6667** |  **30666.6667** |        **390958.69 KB** |
| PooledICollectionConstructor | 100000 |    Int |   127,200.9 us |  2,486.996 us |  4,155.212 us |   124,934.9 us |  1.52 |    0.07 |           - |           - |           - |               40 KB |
|  StackIEnumerableConstructor | 100000 |    Int |   919,865.2 us | 16,018.233 us | 14,199.746 us |   916,968.6 us | 10.89 |    0.27 | 202000.0000 | 154000.0000 | 153000.0000 |        1027684.9 KB |
| PooledIEnumerableConstructor | 100000 |    Int |   969,892.5 us | 17,945.385 us | 17,624.768 us |   962,626.8 us | 11.48 |    0.36 |           - |           - |           - |              120 KB |
|                              |        |        |                |               |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** | **String** |   **561,282.2 us** | **11,523.602 us** | **27,162.487 us** |   **558,502.0 us** |  **1.00** |    **0.00** |  **29000.0000** |  **26000.0000** |  **26000.0000** |         **781535.8 KB** |
| PooledICollectionConstructor | 100000 | String |   320,914.4 us |  3,810.997 us |  3,182.355 us |   320,287.6 us |  0.55 |    0.03 |           - |           - |           - |               40 KB |
|  StackIEnumerableConstructor | 100000 | String | 1,822,410.2 us |  3,777.328 us |  3,533.315 us | 1,823,235.6 us |  3.15 |    0.13 | 333000.0000 | 287000.0000 | 285000.0000 |        2053366.2 KB |
| PooledIEnumerableConstructor | 100000 | String | 2,066,738.5 us |  9,443.189 us |  8,371.141 us | 2,065,016.3 us |  3.58 |    0.15 |           - |           - |           - |              128 KB |