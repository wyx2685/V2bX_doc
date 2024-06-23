# 限速功能说明

1. 用户限速：请在V2board的订阅套餐限速处填写，单位Mbps。
2. 限速值设为0，则为不限速。

## 本地节点限速设置

可以在本地配置文件`SpeedLimit`设置限速。注意此设置会覆盖远程获取的节点级别限速。

{% hint style="info" %}
节点限速：所有连接到该节点的用户限速值都会采用`SpeedLimit`中的设置值\*\*（不是端口限速）\*\*
{% endhint %}

配置文件详见：[配置文件说明](../xrayr-pei-zhi-wen-jian-shuo-ming/config.md#mian-ban-dui-jie-pei-zhi)
