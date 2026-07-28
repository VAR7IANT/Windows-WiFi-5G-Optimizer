# Windows WiFi 5G Optimizer

A one-click Windows batch script that automatically optimizes compatible wireless adapters to prefer the 5 GHz Wi-Fi band and disables common Wi-Fi power-saving options.

[中文说明](#中文说明)

## Features

- Automatically requests administrator privileges
- Detects the active physical wireless adapter
- Attempts to set **Preferred Band** to a 5 GHz option exposed by the adapter driver
- Disables Windows wireless-adapter power saving where supported
- Applies maximum-performance wireless power-plan settings
- Restarts and reconnects the Wi-Fi adapter automatically
- Measures download speed before and after optimization
- Displays the results in a Windows pop-up
- Uses only built-in Windows tools and PowerShell

## Supported systems

- Windows 10
- Windows 11

Actual support depends on the wireless-adapter driver. Some drivers do not expose a writable **Preferred Band** setting, even when the hardware supports 5 GHz Wi-Fi.

## Download and use

1. Download `Windows_WiFi_5G_Optimizer.bat`
2. Double-click the file
3. Accept the Windows administrator prompt
4. Keep the computer connected to Wi-Fi while the script runs
5. Review the before-and-after result shown in the pop-up

The wireless connection is temporarily disconnected while the adapter restarts.

## What the script changes

The script may change the following local Windows settings when supported:

- Wireless-adapter preferred band
- Selective suspend
- Device sleep on disconnect
- The adapter option that allows Windows to turn off the device to save power
- Wireless Adapter Settings power-saving mode in the active Windows power plan

## Important limitations

This project cannot increase the maximum speed provided by your ISP, router, Wi-Fi standard, signal quality, or wireless hardware. A 5 GHz connection can provide higher throughput at short range, but usually has less range and weaker wall penetration than 2.4 GHz.

The included speed test is a quick comparison, not a laboratory benchmark. Results can vary because of server load, signal strength, background downloads, routing, congestion, VPNs, proxies, and router conditions.

## Security and privacy

The script is plain text and can be inspected before execution.

It does not:

- Collect personal information
- Read saved Wi-Fi passwords
- Upload local files
- Install third-party software
- Add startup tasks or background services

Network access is used only for the before-and-after download-speed test.

## Troubleshooting

### The script reports that no preferred-band setting is available

Update the wireless-adapter driver from the computer or adapter manufacturer. If the setting is still unavailable, the driver probably does not expose it to Windows.

### The connection does not return automatically

Reconnect to the Wi-Fi network from the Windows network menu. The saved Wi-Fi profile is not deleted.

### The measured speed is lower after optimization

Run a trusted browser-based speed test several times. Short tests can fluctuate, and 5 GHz may perform worse when the router is far away or separated by several walls.

## Version

Current version: **v1.0.0**

See [CHANGELOG.md](CHANGELOG.md) for release history.

## License

Released under the [MIT License](LICENSE).

---

## 中文说明

Windows WiFi 5G Optimizer 是一个可直接运行的 Windows BAT 工具，用于自动识别无线网卡、尝试将驱动提供的“首选频带”设置为 5 GHz、关闭常见无线网卡省电功能，并在优化前后进行下载测速对比。

### 使用方法

1. 下载 `Windows_WiFi_5G_Optimizer.bat`
2. 双击运行
3. 同意管理员权限请求
4. 等待无线网卡重启并重新连接
5. 查看弹窗中的优化结果

### 注意事项

- 是否能修改首选频带取决于无线网卡驱动
- 运行时 Wi-Fi 会短暂断开
- 5 GHz 通常速度更高，但覆盖距离和穿墙能力通常弱于 2.4 GHz
- 脚本无法突破宽带套餐、路由器、无线网卡或信号条件的物理上限
- 测速结果会受到测速节点、网络占用、代理、VPN 和信号波动影响
