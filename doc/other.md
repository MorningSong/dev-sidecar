# 其他程序使用

## Java程序使用

> 由 [Enaium](https://github.com/Enaium) 提供，未做验证，可供参考

1. 先通过keytool安装证书：

   ```shell
   keytool -import -alias dev-sidecar -keystore "jdk路径\security\cacerts" -file 用户目录\.dev-sidecar\dev-sidecar.ca.crt
   ```
   默认密码为 `changeit`

2. 启动时还需要设置参数，例：

   ```shell
   java -Dhttp.proxyHost=localhost -Dhttp.proxyPort=31181 -Dhttps.proxyHost=localhost -Dhttps.proxyPort=31181 -jar xxxx.jar
   ```

3. Gradle还需在`用户目录/.gradle/gradle.properties`创建配置文件：

    ```properties
    systemProp.http.proxyHost=localhost
    systemProp.http.proxyPort=31181
    systemProp.https.proxyHost=localhost
    systemProp.https.proxyPort=31181
    ```
