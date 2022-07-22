# fiddlerMagisk
fiddler默认证书的Magisk模块，用于将fiddler证书添加进系统证书，使用前请检查证书是否一致，如果不一致需要自行替换其中的证书 `/system/etc/security/cacerts/269953fb.0`

## 使用

下载压缩为xxx.zip，传输至手机后使用magisk安装。z（zip目录要正确，不要多加目录，打开zip就应该是这几个条目）

## 证书制作步骤
### CER格式证书
1. 将cer格式证书转换为pem 

    `openssl x509 -inform der -in FiddlerRoot.cer -out FiddlerRoot.pem`

2. 将pem证书取hash

    `openssl x509 -subject_hash_old -in FiddlerRoot.pem -noout`

3. 使用上面得到的8位hash重命名pem证书为xxxxxxxx.0,并替换 `/system/etc/security/cacerts/269953fb.0`