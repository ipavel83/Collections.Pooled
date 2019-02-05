``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-009812
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |       N |        Mean |       Error |      StdDev | Ratio | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |-------- |------------:|------------:|------------:|------:|------------:|------------:|------------:|--------------------:|
|   **ListAdd** |   **10000** |    **716.8 us** |   **3.1505 us** |   **2.9470 us** |  **1.00** |    **333.0078** |    **333.0078** |    **333.0078** |           **1240160 B** |
| PooledAdd |   10000 |    144.9 us |   0.6016 us |   0.5333 us |  0.20 |           - |           - |           - |                40 B |
|           |         |             |             |             |       |             |             |             |                     |
|   **ListAdd** |  **100000** |  **7,076.1 us** |  **34.2110 us** |  **28.5677 us** |  **1.00** |    **492.1875** |    **492.1875** |    **492.1875** |          **12400160 B** |
| PooledAdd |  100000 |  1,496.2 us |   6.8257 us |   6.3848 us |  0.21 |           - |           - |           - |                40 B |
|           |         |             |             |             |       |             |             |             |                     |
|   **ListAdd** | **1000000** | **70,323.0 us** | **613.4427 us** | **573.8147 us** |  **1.00** |   **1142.8571** |   **1142.8571** |   **1142.8571** |         **124000160 B** |
| PooledAdd | 1000000 | 66,467.1 us | 357.7126 us | 317.1029 us |  0.95 |    875.0000 |    875.0000 |    875.0000 |         125829256 B |