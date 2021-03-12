# TronNet
TronNet is a SDK that includes libraries for working with TRON, TronNet makes it easy to build TRON applications with .net.

## Get Started
### NuGet 

You can run the following command to install the `TronNet` in your project.

```
PM> Install-Package TronNet
```

### Configuration

First,You need to config `TronNet` in your `Startup.cs`:
```c#
......
using StowayNet;
using TronNet;
......

public void ConfigureServices(IServiceCollection services)
{
    ......

    services.AddStowayNet().AddTronNet(x =>
    {
        x.Network = TronNetwork.MainNet;
        x.Channel = new GrpcChannelOption { Host = "grpc.shasta.trongrid.io", Port = 50051 };
        x.SolidityChannel = new GrpcChannelOption { Host = "grpc.shasta.trongrid.io", Port = 50052 };
    });

    ......
}

```

### Sample

#### Sample 1: Generate Address Offline