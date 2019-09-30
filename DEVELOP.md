由于这个项目已经很古老了。想要编译成功也不是这么容易。下面记录下该如何才能编译成功。

## 环境依赖
- Java 1.8
- ant
- Android SDK

**安装Java 1.8的安装**

推荐用[jabba](https://github.com/shyiko/jabba)

```
$ jabba install adopt@1.8.0-222
$ java -version
openjdk version "1.8.0_222"
OpenJDK Runtime Environment (AdoptOpenJDK)(build 1.8.0_222-b10)
OpenJDK 64-Bit Server VM (AdoptOpenJDK)(build 25.222-b10, mixed mode)
```

**安装ApacheAnt**

```
brew install ant
```

**安装Android SDK**

下载安装完Android Studio，Tools->SDK Manager 选择Android-19，下载下来即可。

编译

```
ant build
```


## Common issues
### 如果安装ant时报 bcel 404 Not Found错误的话，需要通过修改Formula来这样修复

```
brew edit ant
```

运行

```
ant build
```

一切顺利的话，就可以在 bin 目录下看到 `bundle.jar`和`uiautomator-stub.jar` 这两个文件了。

### 遇到报错 `“Cannot find build.xml” error building Android SDK sample`
这时需要使用旧版Android SDK目录下的tools文件夹，替换到原来的即可。

参考 <https://stackoverflow.com/questions/43648201/cannot-find-build-xml-error-building-android-sdk-sample>

