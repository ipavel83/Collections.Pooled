``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-009812
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|    Method |       N |   Type |        Mean |      Error |     StdDev |      Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |-------- |------- |------------:|-----------:|-----------:|------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|  **StackPop** |   **10000** |    **Int** |   **143.96 us** |   **5.702 us** |  **16.362 us** |   **142.73 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledPop |   10000 |    Int |   156.97 us |   7.063 us |  20.152 us |   147.32 us |  1.11 |    0.20 |           - |           - |           - |                   - |
|           |         |        |             |            |            |             |       |         |             |             |             |                     |
|  **StackPop** |   **10000** | **String** |    **60.58 us** |   **2.049 us** |   **3.996 us** |    **59.31 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledPop |   10000 | String |   187.93 us |   9.051 us |  25.229 us |   176.37 us |  3.02 |    0.40 |           - |           - |           - |                   - |
|           |         |        |             |            |            |             |       |         |             |             |             |                     |
|  **StackPop** |  **100000** |    **Int** | **1,387.04 us** |  **27.173 us** |  **47.592 us** | **1,401.53 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledPop |  100000 |    Int | 1,485.88 us |  29.550 us |  70.228 us | 1,491.55 us |  1.08 |    0.06 |           - |           - |           - |                   - |
|           |         |        |             |            |            |             |       |         |             |             |             |                     |
|  **StackPop** |  **100000** | **String** |   **598.08 us** |  **11.966 us** |  **17.910 us** |   **587.45 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledPop |  100000 | String |   332.46 us |  12.540 us |  33.254 us |   322.59 us |  0.56 |    0.05 |           - |           - |           - |                   - |
|           |         |        |             |            |            |             |       |         |             |             |             |                     |
|  **StackPop** | **1000000** |    **Int** | **2,915.79 us** | **106.821 us** | **294.217 us** | **2,979.76 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledPop | 1000000 |    Int | 2,970.72 us | 189.402 us | 515.282 us | 2,999.62 us |  1.02 |    0.15 |           - |           - |           - |                   - |
|           |         |        |             |            |            |             |       |         |             |             |             |                     |
|  **StackPop** | **1000000** | **String** | **3,126.32 us** |  **57.042 us** |  **53.357 us** | **3,098.94 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledPop | 1000000 | String | 3,113.35 us |  67.705 us |  56.537 us | 3,094.47 us |  1.00 |    0.02 |           - |           - |           - |                   - |