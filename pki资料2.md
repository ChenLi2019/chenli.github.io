> 在学实践第2周(Linux与Windows初级人员)

---
# 1. 理论和概念学习
> 最主要的学习资源仍然来自
>
> - [PKI资料汇编](http://dev.koal.com/projects/03_pki_application/wiki/PKI%E4%BD%93%E7%B3%BB%E7%BB%BC%E8%BF%B0)
> - \\\\debian.koal.com\training\16_培训资料(2016)\20160104_PKI体系培训之一
> - \\\\debian.koal.com\training\16_培训资料(2016)\20160113_PKI体系培训之二
> - \\\\debian.koal.com\training\16_培训资料(2016)\20160127_PKI体系培训之三

## 1.1 RSA算法
- 学习目标
  - 理解RSA算法原理
  - 掌握RSA算法的公私钥结构
- 参考资料
  - [RSA算法原理（一）](http://www.ruanyifeng.com/blog/2013/06/rsa_algorithm_part_one.html)
  - [RSA算法原理（二）](http://www.ruanyifeng.com/blog/2013/07/rsa_algorithm_part_two.html)
  - [跨越千年的RSA算法](http://www.matrix67.com/blog/archives/5100)
  - [RSA密钥结构(PKCS#1规范)](http://git.koal.com/training/pki-training/wikis/references#pkcs%E7%B3%BB%E5%88%97)

## 1.2 数字签名与数字证书
- 学习目标
  - 理解数字签名的原理
  - 理解证书与数字签名的关系
  - 理解证书的颁发、验证流程
  - 掌握X509数字证书的格式
- 参考资料
  - [数字签名是什么？](http://www.ruanyifeng.com/blog/2011/08/what_is_a_digital_signature.html)
  - [数字证书原理](http://www.cnblogs.com/JeffreySun/archive/2010/06/24/1627247.html)
  - [PKCS系列规范](http://git.koal.com/training/pki-training/wikis/references#pkcs%E7%B3%BB%E5%88%97)
  - [ASN.1与X509](http://git.koal.com/training/pki-training/wikis/asn.1-and-x509)

# 2. 实践
## 2.1 实践2A：使用OpenSSL命令行，构造一张与公司个人证书相同的证书，要求以下5项完全相同
- 证书序列号
- 证书有效期（年月日）
- 证书公钥
- 证书主题项
- 证书颁发者主题项

## 2.2 实践2B：调用OpenSSL的EVP库函数，实现RSA签名
- 将结果采用16进制数和Base64字符串两种模式进行输出
- 支持以下命令行参数
  - -d/--digest  摘要算法（包括SHA1 | SHA256 | SHA512)，默认为SHA256
  - -k/--key     私钥文件（要求能自动适应PEM与DER格式）
  - -i/--input   输入文件
  - -o/--output  输出文件
  - -f/--format  输出/输入格式，包括 BINARY | HEX | BASE64 这三种，默认为BINARY
  - -h/--help 显示使用帮助

- 使用示例：
  xxxxx -d SHA256 -k signer.pem -i input.txt -format BASE64 -out sig.txt

## 2.3 实践2C：调用OpenSSL的X509相关函数，构造实践2A中的证书请求
- 支持以下命令行参数
  - -d/--digest  摘要算法（包括SHA1 | SHA256 | SHA512)，默认为SHA256
  - -k/--key     私钥文件（要求能自动适应PEM与DER格式）
  - -f/--format  输出格式，包括 DER | PEM 这2种，默认为PEM
  - -s/--subject 输入证书请求的DN项（如"CN=xxxx/O=xxxxxxx/OU=XXXXXX"，各项之间使用/分割）
  - -h/--help    显示使用帮助


## 2.4 编程参考资料
- [OpenSSL命令行](http://wiki.koal.com/wiki/index.php/OpenSSL%E5%91%BD%E4%BB%A4%E8%A1%8C)
- [OpenSSL的算法调用](http://wiki.koal.com/wiki/index.php/OpenSSL:%E7%AE%97%E6%B3%95%E8%B0%83%E7%94%A8)
- [OpenSSL的工具函数](http://wiki.koal.com/wiki/index.php/OpenSSL:%E5%B8%B8%E7%94%A8%E5%B7%A5%E5%85%B7%E5%87%BD%E6%95%B0)
- [一本比较完整介绍OpenSSL各类编程的电子书](http://wiki.koal.com/wiki/index.php/%E6%96%87%E4%BB%B6:Secure_Programming_Cookbook_for_C_and_C%2B%2B.pdf)
- [一本中文版的OpenSSL编程指南](http://wiki.koal.com/wiki/index.php/%E6%96%87%E4%BB%B6:OpenSSL%E7%BC%96%E7%A8%8B.pdf)


