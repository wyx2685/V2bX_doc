# 自动申请证书说明

V2bX 支持多种自动申请证书配置。申请到的证书将会放在配置文件`config.json`指定的目录下。

以下是自动申请证书的相关配置文件说明。

```json
      "CertConfig": {
        // 证书申请模式，none、http、dns、self
        "CertMode": "none",
        "RejectUnknownSni": false,
        // 证书域名
        "CertDomain": "test.com",
        // 证书文件目录
        "CertFile": "/etc/V2bX/fullchain.cer",
        // 密钥文件目录
        "KeyFile": "/etc/V2bX/cert.key",
        // 申请证书时使用的用户邮箱
        "Email": "v2bx@github.com",
        // DNS解析提供者 详见https://go-acme.github.io/lego/dns/的CLI flag name列
        "Provider": "cloudflare",

        // DNS解析提供者的环境变量，详见https://go-acme.github.io/lego/dns/，以cloudflare为例
        "DNSEnv": {
          "CF_DNS_API_TOKEN": "1234567890abcdefghijklmnopqrstuvwxyz"
        }
      }
```

| 参数                 | 选项                         | 说明                                                                                                                                                                                              |
| ------------------ | -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `CertMode`         | `none`,`http`,`dns`,`self` | <p>获取证书的方式。</p><p><code>none</code>：强制关闭tls设置。</p><p><code>http</code>：通过http申请，需要80端口。</p><p><code>dns</code>：使用dns模式申请，需要制定相关dns服务商配置。</p><p><code>self</code>:指定文件路径手动提供，若路径无文件则使用自签名证书。</p> |
| `RejectUnknownSni` | `true`, `false`            | Xray内核专用，服务端接收到的 SNI 与证书域名不匹配即拒绝 TLS 握手，默认为`false`。                                                                                                                                             |
| `CertDomain`       | 无                          | 申请证书域名                                                                                                                                                                                          |
| `CertFile`         | 无                          | 手动指定的证书路径                                                                                                                                                                                       |
| `KeyFile`          | 无                          | 手动指定的私钥路径                                                                                                                                                                                       |
| `Provider`         | 无                          | dns提供商，所有支持的dns提供商请在此获取：[https://go-acme.github.io/lego/dns/](https://go-acme.github.io/lego/dns/)                                                                                              |
| `DNSEnv`           | 无                          | 采用DNS申请证书需要的环境变量，请参考上文链接内，自己的dns提供商所需要的参数，填写于此。请注意一行一个，填写时需符合json文件格式。                                                                                                                          |

