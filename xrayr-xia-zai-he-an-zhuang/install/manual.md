# 手动安装

## 下载并使用

1. 在此处，根据自身系统选择合适的版本：[Release](https://github.com/wyx2685/V2bX/releases)
2. 解压压缩包，之后运行：`./V2bX server -c config.json`

## 编译并使用

1. 配置go 1.22.0环境
2.  依次运行

    ```bash
    git clone https://github.com/wyx2685/V2bX
    cd V2bX
    go mod tidy
    go build -v -o ./V2bX -tags "sing hysteria2 with_reality_server with_quic with_grpc with_utls with_wireguard with_acme" -trimpath -ldflags "-s -w -buildid="
    ./V2bX server -c config.json
    ```

配置文件详见：[配置文件说明](../../xrayr-pei-zhi-wen-jian-shuo-ming/config.md)
