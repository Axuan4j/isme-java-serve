## 创建密钥文件

安装openssl

```
# Ubuntu/Debian系
sudo apt-get update
sudo apt-get install openssl
# CentOS系
sudo yum install openssl
# MacOS
brew install openssl
```

生成RSA密钥对

```
openssl genpkey -algorithm RSA -out private_key.pem -aes256 -pkeyopt rsa_keygen_bits:2048
```

参数解释:

* -algorithm RSA：指定使用 RSA 算法。
* -out private_key.pem：指定输出文件名为 private_key.pem。
* -aes256：使用 AES-256 加密私钥，增加安全性。
* -pkeyopt rsa_keygen_bits:2048：指定密钥长度为 2048 位。
* 运行上述命令后，系统会提示你输入一个密码来保护私钥。请记住这个密码，后续使用私钥时需要输入。

生成公钥

```
openssl rsa -pubout -in private_key.pem -out public_key.pem
```

* -pubout：指定提取公钥。
* -in private_key.pem：指定输入文件为 private_key.pem。
* -out public_key.pem：指定输出文件为 public_key.pem。
* 运行上述命令后，系统会提示你输入之前设置的私钥密码。
