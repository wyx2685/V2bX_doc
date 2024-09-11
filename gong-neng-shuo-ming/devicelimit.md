# 设备连接限制功能说明

## 全局设备限制

当[V2board](https://github.com/wyx2685/v2board)订阅套餐中设备数限制＞0时，V2bX将会启用全局设备限制功能。此时，不同后端节点将全局限制独立IP连接数量。

根据需要选择[V2board](https://github.com/wyx2685/v2board)全局设备数限制采用宽松模式：

* 关闭：1个IP在多个节点同时使用，统计为多台设备
* 开启：1个IP在多个节点同时使用，仅统计为1台设备

<figure><img src="../.gitbook/assets/宽松模式.JPG" alt=""><figcaption></figcaption></figure>

当设备限制为1时，不同节点之间的切换会受到限制，建议至少设置设备数限制为2。

由于V2boad面板限制，IP连接信息可能需要至少2分钟才能传递到全部的后端节点，因此在2分钟内的同时连接将不能被限制。
