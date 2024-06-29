<p align="center">
   <br> <a href="README_CN.md">中文</a> | English
</p>

# ExCloudflareWarpSpeedTest

*我担心这个改版可能太个性化了于是没有 PR 回去，如果原作者看到了愿意 merge 可以发 issue 联系我😊*

## Introduction

Cloudflare WARP Speed Test is a command-line tool for testing the latency and speed of Cloudflare WARP IP addresses and obtaining information about the minimum latency and available ports, then automatically set the best endpoint and try to connect. It provides various options to customize test parameters and filter results based on specific conditions.

Inspired(Copied) by [CloudflareSpeedTest](https://github.com/XIU2/CloudflareSpeedTest)

Modified from [peanut996/CloudflareWarpSpeedTest](https://github.com/peanut996/CloudflareWarpSpeedTest)

> Modification:
>
> Now the program will automatically set the best endpoint and try to connect.
>
> Reduce the default number of addresses to be scanned to 2500. Because in present situation, too long a scan time may cause the previous IP to become invalid.
>
> README.md (Obviously)
>
> Automatically disable warp before testing speed to avoid interference.
>
> Increase the number of testing threads by default.

## Usage

To use ExCloudflareWarpSpeedTest, you can run the following command-line options:

```bash
CloudflareWarpSpeedTest -n 500 -t 10 -c 2500 -tl 300 -q -tll 0 -tlr 0.2 -p 10 -f ip.txt -ip 1.1.1.1 -o result.csv -all
```

Here is an explanation of the main available options:

+ `-n`        500: Specifies the number of latency test threads. Increasing this value can speed up the latency testing process, but it may not be suitable for lower-performance devices like routers. The default value is 500, with a maximum of 1000.
+ `-t`        10: Sets the number of times latency tests are performed for each IP address. The default value is 10 times.
+ `-c`        2500: The addressed number to be scanned. The default value is 2500.
+ `-ipv6`     IPv6 mode. Only scan ipv6 addresses.
+ `-o`        result.csv: Sets the output result file. The default file is \"result.csv\".
+ `-all`      This flag indicates that all ip and port will be scanned.
+ `-pri`      Custom Wireguard private key.
+ `-pub`      Custom Wireguard public key. Default is the Warp public key.
+ `-reserved` Custom Reserved. Format: `[0, 0, 0]`

For more usage instructions, please use `-h`.

## Note

Please note that adjusting test parameters can affect test speed and results. Choosing the appropriate settings is crucial based on the performance of your device and the specific conditions you want to apply.

**Disclaimer**: This tool is not affiliated with or endorsed by Cloudflare. Please use it responsibly and comply with their terms of service.

## License

This software is released under the [GPL v3 license](LICENSE).
