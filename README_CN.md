<p align="center">
   <br>  中文 | <a href="README.md">English</a>
</p>

# ExCloudflareWarpSpeedTest

## 简介

ExCloudflare WARP 速度测试是一个命令行工具，用于测试 Cloudflare WARP IP 地址的延迟和速度，并获取关于最低延迟和可用端口的信息，并且自动设置并连接。它提供了各种选项，以自定义测试参数并根据特定条件筛选结果。

Inspired(Copied) by [CloudflareSpeedTest](https://github.com/XIU2/CloudflareSpeedTest)

Modified from [peanut996/CloudflareWarpSpeedTest](https://github.com/peanut996/CloudflareWarpSpeedTest)

> 修改之处：
>
> 测速后自动选择最佳 IP 连接
>
> 修改了自述文档
>
> 在测速前自动关闭 warp 以免干扰
>
> 增加默认测速线程数
>
> 新增 FastMode 模式，发现可用 IP 后立即连接，以避免等待扫描完毕的时间内 IP 失效

## 用法

要使用 ExCloudflareWarpSpeedTest，您可以运行以下命令行选项

```bash
ExCloudflareWarpSpeedTest -n 300 -t 10 -c 2500 -tl 300 -q -tll 0 -tlr 0.2 -p 10 -f ip.txt -ip 1.1.1.1 -o result.csv -all
```

以下是主要可用选项的解释：

+ `-n`        500：指定延迟测试线程的数量。增加此值可以加快延迟测试过程，但不适合性能较低的设备，如路由器。默认值为 500，最大为 1000。
+ `-t`        10：设置对每个 IP 地址执行延迟测试的次数。默认值为 10 次。
+ `-c`        2500: 扫描地址的个数。默认为2500个。
+ `-ipv6`     ipv6模式：仅扫描ipv6地址。
+ `-o`        result.csv：设置输出结果文件。默认文件为 "result.csv"。
+ `-all`      此标志表示应测试所有的IP和端口的组合。
+ `-pri`      自定义wireguard的私钥。
+ `-pub`      自定义wireguard的公钥。默认为WARP的公钥。
+ `-reserved` 自定义Reserved字段。格式为 `[0, 0, 0]`

更多使用说明请使用 `-h`。

## 注意

请注意，调整测试参数可能会影响测试速度和结果。根据设备的性能和您希望应用的特定条件选择合适的设置至关重要。

**免责声明**： 本工具与 Cloudflare 无关，也未得到其认可。请负责任地使用并遵守其服务条款。

## License

此软件根据 [GPL v3 许可证](LICENSE) 发布
