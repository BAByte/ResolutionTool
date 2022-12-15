基于这个做了点修改：

[(Android 屏幕适配方案_鸿洋_的博客-CSDN博客_安卓游戏怎么屏幕适配](https://blog.csdn.net/lmj623565791/article/details/45460089)

# 打包jar：

1. javac ./GenerateValueFiles.java
2. 新建一个test文件夹，把上一步生成的.class文件,放到test文件夹中。（注：test是GenerateValueFiles.java的包路径，你可以打开这个java文件看看）

3.测试是否能运行：java test.GenerateValueFiles

4.打包出jar：jar -cef test.GenerateValueFiles autolayout.jar test

# 生成分辨率

横竖屏时，系统会自己选择相关文件，所以生成的分辨率文件夹一定是 w > h的

## 当设计稿是横屏：1920 * 1200

生成常用分辨率values文件夹的命令：
java -jar autolayout.jar 1920 1200

生成特殊的分辨率values文件夹的命令：
java -jar autolayout.jar 1920 1200 w,h_w,h

例如你需要1080p的分辨率设备，这里应该是：java -jar autolayout.jar 1920 1200 1920,1080

## 当设计稿是竖屏： 1200 * 1920

生成常用分辨率values文件夹的命令：
java -jar autolayout.jar 1200 1920

生成特殊的分辨率values文件夹的命令：
java -jar autolayout.jar 1200 1900 w,h_w,h

例如你需要1080p的分辨率设备，这里应该是：java -jar autolayout.jar 1200 1920 1920,1080
