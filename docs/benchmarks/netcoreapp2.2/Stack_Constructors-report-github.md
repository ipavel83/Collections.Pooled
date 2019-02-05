``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-010184
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|                       Method |      N |   Type |           Mean |         Error |         StdDev | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|----------------------------- |------- |------- |---------------:|--------------:|---------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackICollectionConstructor** |   **1000** |    **Int** |       **260.5 us** |     **2.2715 us** |      **2.0136 us** |  **1.00** |    **0.00** |   **1290.0391** |           **-** |           **-** |          **3968.75 KB** |
| PooledICollectionConstructor |   1000 |    Int |       133.8 us |     0.6078 us |      0.5685 us |  0.51 |    0.00 |     12.6953 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 |    Int |     6,952.4 us |    28.6302 us |     26.7807 us | 26.68 |    0.27 |   2687.5000 |           - |           - |          8273.44 KB |
| PooledIEnumerableConstructor |   1000 |    Int |     7,308.3 us |    26.6637 us |     23.6367 us | 28.05 |    0.24 |     31.2500 |           - |           - |           117.19 KB |
|                              |        |        |                |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |   **1000** | **String** |       **646.8 us** |     **8.8163 us** |      **7.8154 us** |  **1.00** |    **0.00** |   **2556.6406** |           **-** |           **-** |             **7875 KB** |
| PooledICollectionConstructor |   1000 | String |       601.4 us |     3.3507 us |      3.1342 us |  0.93 |    0.01 |     12.6953 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |   1000 | String |    11,917.4 us |    49.2369 us |     46.0563 us | 18.43 |    0.20 |   5281.2500 |           - |           - |         16265.63 KB |
| PooledIEnumerableConstructor |   1000 | String |    13,222.6 us |    26.8531 us |     22.4236 us | 20.44 |    0.26 |     31.2500 |           - |           - |              125 KB |
|                              |        |        |                |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** |    **Int** |     **2,634.4 us** |    **17.4113 us** |     **15.4346 us** |  **1.00** |    **0.00** |  **12656.2500** |           **-** |           **-** |            **39125 KB** |
| PooledICollectionConstructor |  10000 |    Int |     1,136.3 us |     3.0355 us |      2.8394 us |  0.43 |    0.00 |     11.7188 |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |  10000 |    Int |    69,160.9 us |   188.7134 us |    176.5226 us | 26.25 |    0.15 |  41625.0000 |           - |           - |        128367.19 KB |
| PooledIEnumerableConstructor |  10000 |    Int |    74,347.8 us |   278.5278 us |    260.5351 us | 28.23 |    0.18 |           - |           - |           - |           117.19 KB |
|                              |        |        |                |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** |  **10000** | **String** |     **6,323.8 us** |    **32.3181 us** |     **30.2303 us** |  **1.00** |    **0.00** |  **24992.1875** |           **-** |           **-** |          **78187.5 KB** |
| PooledICollectionConstructor |  10000 | String |     7,967.2 us |    56.2930 us |     52.6565 us |  1.26 |    0.01 |           - |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor |  10000 | String |   170,832.4 us |   680.6058 us |    636.6391 us | 27.01 |    0.18 |  41333.3333 |  41333.3333 |  41333.3333 |        256359.38 KB |
| PooledIEnumerableConstructor |  10000 | String |   141,983.9 us |   339.7179 us |    283.6799 us | 22.44 |    0.10 |           - |           - |           - |              125 KB |
|                              |        |        |                |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** |    **Int** |   **158,179.8 us** | **2,262.4338 us** |  **2,116.2820 us** |  **1.00** |    **0.00** |  **37500.0000** |  **37500.0000** |  **37500.0000** |        **390942.51 KB** |
| PooledICollectionConstructor | 100000 |    Int |    14,141.4 us |    69.2764 us |     57.8489 us |  0.09 |    0.00 |           - |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor | 100000 |    Int | 1,014,694.8 us | 5,969.0409 us |  5,291.3993 us |  6.42 |    0.10 | 221000.0000 | 180000.0000 | 179000.0000 |       1025124.16 KB |
| PooledIEnumerableConstructor | 100000 |    Int |   736,485.1 us | 2,047.5467 us |  1,709.7942 us |  4.66 |    0.07 |           - |           - |           - |           117.19 KB |
|                              |        |        |                |               |                |       |         |             |             |             |                     |
|  **StackICollectionConstructor** | **100000** | **String** |   **379,340.3 us** | **7,449.4310 us** | **13,807.9979 us** |  **1.00** |    **0.00** |  **20000.0000** |  **20000.0000** |  **20000.0000** |        **781429.19 KB** |
| PooledICollectionConstructor | 100000 | String |    81,412.9 us |   226.8668 us |    212.2113 us |  0.22 |    0.01 |           - |           - |           - |            39.06 KB |
|  StackIEnumerableConstructor | 100000 | String | 1,854,458.6 us | 4,790.4896 us |  4,246.6443 us |  4.93 |    0.31 | 375000.0000 | 335000.0000 | 332000.0000 |       2049582.38 KB |
| PooledIEnumerableConstructor | 100000 | String | 1,298,673.2 us | 3,243.6886 us |  3,034.1483 us |  3.45 |    0.21 |           - |           - |           - |              125 KB |