
# 协议

```text
modbus
snmp
以太网
tcp/ip
rpc协议
```

# modbus
```text
按照modbus协议规范进行数据解析就好了，modbus返回数据的一般格式，一字节的设备ID，一字节指令码，一字节数据长度，然后就是数据区，数据区字节数根据读取的寄存器数量不同 ，长度不同，最后两个字节是CRC16校验码。比如你使用03码读取连续五个寄存器，返回的数据指令码就是03，数据区长度就是寄存器数量乘2，共计十个字节。对于数据解析，先要弄清前端设备寄存器变量类型 ，浮点数，长整数或者整数等 ，浮点数和长整数需要四字节，占用两个寄存器，需要讲两个寄存器的值转换为一个浮点数或长整数。
```