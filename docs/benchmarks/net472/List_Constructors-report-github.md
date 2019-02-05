``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3324.0

Job=Clr  Runtime=Clr  

```
|                       Method |      N |   Type |           Mean |        Error |       StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |------- |------- |---------------:|-------------:|-------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|   **ListICollectionConstructor** |   **1000** |    **Int** |       **249.4 us** |     **1.986 us** |     **1.858 us** |  **1.00** |    **0.00** |   **1290.0391** |           **-** |           **-** |          **3968.97 KB** |
| PooledICollectionConstructor |   1000 |    Int |     1,010.3 us |     6.222 us |     5.820 us |  4.05 |    0.03 |     11.7188 |           - |           - |            39.06 KB |
|   ListIEnumerableConstructor |   1000 |    Int |     9,270.6 us |    50.859 us |    39.707 us | 37.12 |    0.31 |   2687.5000 |           - |           - |          8274.68 KB |
| PooledIEnumerableConstructor |   1000 |    Int |     8,736.9 us |    42.131 us |    37.348 us | 35.02 |    0.27 |     15.6250 |           - |           - |            78.13 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|   **ListICollectionConstructor** |   **1000** | **String** |       **733.8 us** |     **3.080 us** |     **2.881 us** |  **1.00** |    **0.00** |   **2556.6406** |           **-** |           **-** |          **7876.88 KB** |
| PooledICollectionConstructor |   1000 | String |     2,749.0 us |    13.341 us |    11.140 us |  3.74 |    0.02 |     11.7188 |           - |           - |            39.06 KB |
|   ListIEnumerableConstructor |   1000 | String |    13,073.3 us |    47.268 us |    44.215 us | 17.82 |    0.09 |   5281.2500 |           - |           - |         16271.19 KB |
| PooledIEnumerableConstructor |   1000 | String |    15,737.1 us |    93.505 us |    87.464 us | 21.45 |    0.16 |           - |           - |           - |               86 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|   **ListICollectionConstructor** |  **10000** |    **Int** |     **2,628.3 us** |    **11.838 us** |    **11.073 us** |  **1.00** |    **0.00** |  **12656.2500** |           **-** |           **-** |         **39210.66 KB** |
| PooledICollectionConstructor |  10000 |    Int |    14,402.7 us |    37.464 us |    35.044 us |  5.48 |    0.03 |           - |           - |           - |            39.13 KB |
|   ListIEnumerableConstructor |  10000 |    Int |    91,194.9 us |   361.617 us |   320.564 us | 34.69 |    0.20 |  41500.0000 |           - |           - |        128520.83 KB |
| PooledIEnumerableConstructor |  10000 |    Int |    89,481.3 us |   316.164 us |   295.740 us | 34.05 |    0.22 |           - |           - |           - |            78.67 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|   **ListICollectionConstructor** |  **10000** | **String** |     **7,163.5 us** |    **26.608 us** |    **23.587 us** |  **1.00** |    **0.00** |  **24992.1875** |           **-** |           **-** |         **78371.88 KB** |
| PooledICollectionConstructor |  10000 | String |    36,377.6 us |   176.753 us |   165.334 us |  5.08 |    0.03 |           - |           - |           - |            39.43 KB |
|   ListIEnumerableConstructor |  10000 | String |   189,904.8 us |   800.833 us |   749.100 us | 26.52 |    0.15 |  41333.3333 |  41333.3333 |  41333.3333 |        256378.94 KB |
| PooledIEnumerableConstructor |  10000 | String |   172,146.2 us |   745.476 us |   697.318 us | 24.03 |    0.12 |           - |           - |           - |               88 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|   **ListICollectionConstructor** | **100000** |    **Int** |    **63,122.9 us** |   **829.322 us** |   **775.748 us** |  **1.00** |    **0.00** |  **23375.0000** |  **23000.0000** |  **23000.0000** |        **390887.31 KB** |
| PooledICollectionConstructor | 100000 |    Int |   121,618.0 us |   412.661 us |   386.004 us |  1.93 |    0.02 |           - |           - |           - |               40 KB |
|   ListIEnumerableConstructor | 100000 |    Int | 1,024,316.6 us | 4,937.854 us | 4,618.872 us | 16.23 |    0.24 | 201000.0000 | 160000.0000 | 158000.0000 |       1027312.68 KB |
| PooledIEnumerableConstructor | 100000 |    Int |   823,903.3 us | 1,300.813 us | 1,015.589 us | 13.03 |    0.16 |           - |           - |           - |               80 KB |
|                              |        |        |                |              |              |       |         |             |             |             |                     |
|   **ListICollectionConstructor** | **100000** | **String** |   **474,797.7 us** | **2,872.029 us** | **2,686.498 us** |  **1.00** |    **0.00** |  **27000.0000** |  **27000.0000** |  **27000.0000** |        **781554.25 KB** |
| PooledICollectionConstructor | 100000 | String |   313,918.8 us |   827.963 us |   733.968 us |  0.66 |    0.00 |           - |           - |           - |               40 KB |
|   ListIEnumerableConstructor | 100000 | String | 1,713,353.5 us | 3,670.309 us | 3,064.874 us |  3.61 |    0.02 | 330000.0000 | 288000.0000 | 285000.0000 |        2053753.8 KB |
| PooledIEnumerableConstructor | 100000 | String | 1,568,890.4 us | 8,023.752 us | 6,700.197 us |  3.31 |    0.02 |           - |           - |           - |               88 KB |