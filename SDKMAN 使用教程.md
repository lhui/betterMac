> SDKMAN 是一个 SDK 的管理工具，SDKMAN 对于 SDK 相当于 homebrew 对于 mac 上面的软件，可以将其称 sdk 的管理工具，我使用 SDKMAN 的主要的目的是管理 JAVA 的版本，本文的主要的目的也是管理 Java 版本的工具。
>

本文仅适用于 MacOS (类 Unix 系统) 的 操作系统

SDKMAN 的使用教程主要分为安装和使用这两个步骤，或者还有第三个步骤是删除

SDKMAN 参考链接 [sdkman](https://sdkman.io/install)

## 1. 安装 SDKMAN

```bash
curl -s "https://get.sdkman.io" | bash # 下载并执行
source "$HOME/.sdkman/bin/sdkman-init.sh" # 更新环境变量
sdk version # 查看SDK 版本
```

显示效果如下

```bash
SDKMAN 5.xx.x
```

显示上述的内容则证明安装成功

## 2. 安装 JDK

### 2.1 列出当下版本的 jdk

首先查看现在所有的 JDK 版本

```bash
sdk list java
```

显示效果如下：

```bash
================================================================================
Available Java Versions
================================================================================
 Vendor        | Use | Version      | Dist    | Status     | Identifier
--------------------------------------------------------------------------------
 AdoptOpenJDK  |     | 16.0.1.j9    | adpt    |            | 16.0.1.j9-adpt
               |     | 16.0.1.hs    | adpt    |            | 16.0.1.hs-adpt
               |     | 11.0.11.j9   | adpt    |            | 11.0.11.j9-adpt
               | >>> | 11.0.11.hs   | adpt    | installed  | 11.0.11.hs-adpt
               |     | 8.0.292.j9   | adpt    |            | 8.0.292.j9-adpt
               |     | 8.0.292.hs   | adpt    | installed  | 8.0.292.hs-adpt
 Corretto      |     | 17.0.0.35.2  | amzn    |            | 17.0.0.35.2-amzn
               |     | 16.0.2.7.1   | amzn    |            | 16.0.2.7.1-amzn
               |     | 11.0.12.7.2  | amzn    |            | 11.0.12.7.2-amzn
               |     | 8.302.08.1   | amzn    |            | 8.302.08.1-amzn
 GraalVM       |     | 21.2.0.r16   | grl     |            | 21.2.0.r16-grl
               |     | 21.2.0.r11   | grl     |            | 21.2.0.r11-grl
               |     | 20.3.3.r11   | grl     |            | 20.3.3.r11-grl
               |     | 19.3.6.r11   | grl     |            | 19.3.6.r11-grl
 Java.net      |     | 18.ea.18     | open    |            | 18.ea.18-open
               |     | 18.ea.17     | open    |            | 18.ea.17-open
               |     | 18.ea.2.lm   | open    |            | 18.ea.2.lm-open
               |     | 17           | open    |            | 17-open
               |     | 17.ea.3.pma  | open    |            | 17.ea.3.pma-open
               |     | 16.0.2       | open    |            | 16.0.2-open
               |     | 11.0.2       | open    |            | 11.0.2-open
 Liberica      |     | 17.0.0.fx    | librca  |            | 17.0.0.fx-librca
               |     | 17.0.0       | librca  |            | 17.0.0-librca
               |     | 16.0.2.fx    | librca  |            | 16.0.2.fx-librca
               |     | 16.0.2       | librca  |            | 16.0.2-librca
               |     | 11.0.12.fx   | librca  |            | 11.0.12.fx-librca
               |     | 11.0.12      | librca  |            | 11.0.12-librca
               |     | 8.0.302.fx   | librca  |            | 8.0.302.fx-librca
               |     | 8.0.302      | librca  |            | 8.0.302-librca
 Liberica NIK  |     | 21.2         | nik     |            | 21.2-nik
 Microsoft     |     | 17.0.0       | ms      |            | 17.0.0-ms
               |     | 16.0.2.7.1   | ms      |            | 16.0.2.7.1-ms
               |     | 11.0.12.7.1  | ms      |            | 11.0.12.7.1-ms
 Oracle        |     | 17.0.0       | oracle  | installed  | 17.0.0-oracle
 SapMachine    |     | 17           | sapmchn |            | 17-sapmchn
               |     | 16.0.2       | sapmchn |            | 16.0.2-sapmchn
               |     | 11.0.12      | sapmchn |            | 11.0.12-sapmchn
 Semeru        |     | 16.0.2       | sem     |            | 16.0.2-sem
               |     | 11.0.12      | sem     |            | 11.0.12-sem
               |     | 8.0.302      | sem     |            | 8.0.302-sem
 Temurin       |     | 17.0.0       | tem     |            | 17.0.0-tem
               |     | 16.0.2       | tem     |            | 16.0.2-tem
               |     | 11.0.12      | tem     |            | 11.0.12-tem
               |     | 8.0.302      | tem     |            | 8.0.302-tem
 Trava         |     | 11.0.9       | trava   |            | 11.0.9-trava
               |     | 8.0.232      | trava   |            | 8.0.232-trava
 Zulu          |     | 17.0.0       | zulu    |            | 17.0.0-zulu
               |     | 17.0.0.fx    | zulu    |            | 17.0.0.fx-zulu
               |     | 16.0.2       | zulu    |            | 16.0.2-zulu
               |     | 16.0.2.fx    | zulu    |            | 16.0.2.fx-zulu
               |     | 11.0.12      | zulu    |            | 11.0.12-zulu
               |     | 11.0.12.fx   | zulu    |            | 11.0.12.fx-zulu
               |     | 8.0.302      | zulu    |            | 8.0.302-zulu
               |     | 8.0.302.fx   | zulu    |            | 8.0.302.fx-zulu
               |     | 7.0.312      | zulu    |            | 7.0.312-zulu
================================================================================
Omit Identifier to install default version 17.0.0-tem:
    $ sdk install java
Use TAB completion to discover available versions
    $ sdk install java [TAB]
Or install a specific version by Identifier:
    $ sdk install java 17.0.0-tem
Hit Q to exit this list view
================================================================================
```

use `>>>` 指的是现在环境变量中使用的版本

Status `installed` 指的是现在已经安装的软件

### 安装特定版本的 jdk

主要的内容还是上述的 list 的最后一列为指定的版本号

安装命令

```bash
sdk install java 11.0.11.hs-adpt # 安装adpt 的 Java11 版本
```

我安装的时候 oracle 家的只有 17 版本 安装命令如下

```bash
sdk install java 17.0.0-oracle
```

## 3. 切换版本

```bash
 sdk use java 17.0.0-oracle
```

显示返回值如下：

```bash
Using java version 17.0.0-oracle in this shell.
```

使用 java -version 查看 Java 版本

```bash
java version "17" 2021-09-14 LTS
Java(TM) SE Runtime Environment (build 17+35-LTS-2724)
Java HotSpot(TM) 64-Bit Server VM (build 17+35-LTS-2724, mixed mode, sharing)
```

主要参考 SDKMAN 官网
