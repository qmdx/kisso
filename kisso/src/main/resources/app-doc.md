
授权认证方式采用微信机制，客户端认证代码


1、授权

grant_type		授权类型 （client_credential 客户端认证）
app_id			应用ID
app_secret		应用密钥



# 使用AES加密时，当密钥大于128时，代码会抛出异常：java.security.InvalidKeyException: Illegal key size

> 是指密钥长度是受限制的，java运行时环境读到的是受限的policy文件。文件位于${java_home}/jre/lib/security 
这种限制是因为美国对软件出口的控制。 

> 解决办法：http://www.oracle.com/technetwork/java/javaseproducts/downloads/index.html
  进入 Oracle JDK 下载 Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files
  for JDK/JRE 8 【下载对应 JDK 版本的 Policy 文件】
  JDK8 下载地址：http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html
  下载包的readme.txt 有安装说明。就是替换${java_home}/jre/lib/security/ 下面的local_policy.jar和US_export_policy.jar 
