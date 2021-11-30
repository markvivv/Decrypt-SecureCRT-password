# 解密SecureCRT保存的密码

## 1. 前置条件

- 准备好Python3环境

## 2. 安装依赖包

```shell
pip3 install pycryptodome
```

## 3. 下载SecureCRTCipher.py脚本

[SecureCRTCipher.py](https://github.com/xieshaohu/Decrypt-SecureCRT-password/blob/87bf032415243123188a27d115f22d9618331d91/SecureCRTCipher.py)

## 4. 确认配置文件路径路径

打开 `SecureCRT` > `Options` > `Global Options` > `Configuration folder` ，获取配置文件路径

## 5. 打开 `*.ini` 配置文件，获取加密的密码

```config
S:"Password V2"=02:******
```

*02:之后的字符串就是加密密码*

## 6. 执行python脚本进行解密

```shell
python3 SecureCRTCipher.py dec -v2 ******
```

## 7. 注意事项
- 由于 SecureCRT 默认是没有配置 `Configuration Passphrase` 的，所以我们在执行命令的时候，默认不需要加 `-p` 参数
